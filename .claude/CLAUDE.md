# legal — instructions for every session in this repo

## This repo is PUBLIC and it is a live website

GitHub Pages publishes this repo. `privacy.html` and `terms.html` are the
privacy policy and terms of use that third-party app registrations cite, so:

- **Everything committed here is published to the internet.** Never commit
  credentials, client names, client data, or local file paths.
- **Do not rename, move or delete `privacy.html` or `terms.html`.** External
  registrations point at those exact addresses; breaking them is not visible
  from here.
- Any Markdown file outside a dot-folder is published as a web page. This file
  lives in `.claude/` for exactly that reason.

## Parallel sessions: work in a worktree

More than one Claude session can run against a repo at once. When they share
one folder, one session can commit another's unfinished work between two of its
commands.

**If you will EDIT files, and another session may be working in this repo — or
you have been told you are a fork — call EnterWorktree before your first edit.**
When in doubt, use one.

1. **EnterWorktree** with a short task name. Do all edits and commits in the
   worktree it creates, on its own branch.
2. **When the work is done and verified, merge it into `main`** from the main
   checkout, then push. If git reports a conflict, stop and ask; do not resolve
   another session's work by guessing.
3. **Remove the worktree and its branch** once merged.

## Before every commit and every push

- **Re-run `git status` and `git log origin/main..HEAD` immediately before**,
  not once at the start. Another session can change the repo mid-task.
- **If git contradicts what you just saw, read `git reflog` first.** It is
  almost always a second writer, not corruption. Never force, never reset.
- **Check `git remote get-url origin` points at the `C13-Inc` organization.**
- **Never force-push `main`** — a bad push here takes the live pages with it.

## Push `main` promptly

A new worktree branches from `origin/main`, not local `main`, so a commit left
unpushed is invisible to every worktree created after it.
