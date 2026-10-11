# Keeping a fork in sync

If you forked this repo and want your `main` to match upstream (`famelack/famelack-data`):

```bash
# One-time: add the upstream remote (skip if it already exists)
git remote add upstream https://github.com/famelack/famelack-data.git

# Fetch latest from upstream
git fetch upstream

# Update local main onto upstream/main
git checkout main
git rebase upstream/main

# Push the updated main to your fork
git push origin main
```

## Notes

- If you have **no unique commits** on your fork (only behind upstream), the rebase fast-forwards cleanly.
- If you **do** have local commits, rebase replays them on top of upstream. Resolve any conflicts, then `git rebase --continue`.
- If Git refuses a normal push after a rebase that rewrote history, use `git push --force-with-lease origin main` (only on your fork).
