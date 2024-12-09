# No Diff of Lock Files

Lock files include `package-lock.json`, `yarn-lock.json`, `pnpm-lock.yaml`, etc. Generally, they should be tracked by Git. Developers are interested in knowing whether these files have changed. However, the exact diffs, such as those output by commands such as `git show` and `git diff`, are usually irrelevant to developers. Hence, we can stop Git from displaying the diffs of these files by adding the lock files to `.gitattributes` located at the root of the Git repository:

```glogit
package-lock.json binary
yarn-lock.json binary
pnpm-lock.yaml binary
```

After making these changes, Git will only show whether the file has changed or not, similar to the following:

```log
diff --git a/package-lock.json b/package-lock.json
index f77c979af1ba..4b8ba602b6e3 100644
Binary files a/package-lock.json and b/package-lock.json differ
```
