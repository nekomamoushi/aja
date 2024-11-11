# Stashing Untracked files

To stash changes, including untracked files, you need to use the `--include-untracked` or `-u` option with `git stash`. This command saves both your staged and unstaged changes, as well as any files in the working directory that Git is not tracking.

```bash
git stash -u
```
