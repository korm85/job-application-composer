---
name: push-project-to-github
description: Use when the user asks to push, upload, or put a project on GitHub, or wants anyone cloning the repo to have full session parity with the current local state
---

# Push Project to GitHub with Full Parity

## Overview

"Full parity" means a cloned repo produces an identical Claude Code session to the current local one — same code, same instructions, same memory context. The critical gap most agents miss: Claude's memory files live **outside** the project directory and must be explicitly copied in.

## Full Parity Checklist

Before pushing, ensure the repo contains:

| Component | Location in repo | Source |
|---|---|---|
| All project files | (wherever they are) | local project |
| `CLAUDE.md` | project root | write/update |
| Memory files | `.claude/memory/` | `~/.claude/projects/<encoded-path>/memory/` |
| `README.md` | project root | write if missing |

## Step-by-Step

### 1. Find and copy memory files

Memory lives outside the project. Find the encoded path:
```bash
# Encode the project path: replace / with - (leading / becomes leading -)
# /home/user/my-project → -home-user-my-project
ls ~/.claude/projects/
```

Copy into the repo:
```bash
mkdir -p <project-root>/.claude/memory
cp ~/.claude/projects/<encoded-path>/memory/*.md <project-root>/.claude/memory/
```

### 2. Update CLAUDE.md

Add at the top of the "Start of every session" section — memory files must be read **first**, before any project files:

```markdown
## Start of every session

Read in order:
1. `.claude/memory/user_*.md` — who the user is
2. `.claude/memory/project_*.md` — project status and context
3. [project-specific files...]
```

### 3. Create GitHub repo

**If `$GITHUB_TOKEN` or `$GH_TOKEN` is set:**
```bash
curl -s -X POST \
  -H "Authorization: token $GITHUB_TOKEN" \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/user/repos \
  -d '{"name":"<repo-name>","description":"<desc>","private":false,"auto_init":false}' \
  | python3 -c "import sys,json; d=json.load(sys.stdin); print(d.get('html_url', d.get('message','')))"
```

Get username first if needed:
```bash
curl -s -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user | python3 -c "import sys,json; print(json.load(sys.stdin)['login'])"
```

**If `gh` CLI is available:** `gh repo create <name> --public`

**Otherwise:** Ask user to create repo on GitHub and paste the URL.

### 4. Init, commit, push

```bash
git init
git add -A
git commit -m "Initial snapshot — <date>

<one-line description of what's in the repo>

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>"
git remote add origin https://<username>:$GITHUB_TOKEN@github.com/<username>/<repo>.git
git branch -M main
git push -u origin main
```

## Common Mistakes

| Mistake | Fix |
|---|---|
| Forgetting memory files | Always check `~/.claude/projects/` before pushing |
| Memory files in CLAUDE.md but not committed | `git add .claude/memory/` explicitly |
| CLAUDE.md doesn't reference memory files | Add to "Start of every session" section |
| Pushing token in remote URL to public repo | Token in remote URL is local only — not committed, safe |

## Verification

After pushing, confirm:
```bash
git ls-files | grep ".claude/memory"   # should list memory files
git ls-files | grep "CLAUDE.md"        # should exist
```

Then test: `git clone <url> /tmp/test-clone && cat /tmp/test-clone/CLAUDE.md`
