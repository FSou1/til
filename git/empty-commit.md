# How to push an empty commit

On my current project you need to push a commit with the title "update screenshots" to start an extra step in the pipeline.

The `--allow-empty` flag could be used for it:

```
git commit --allow-empty -m "My empty commit with a message"
```

References:
* https://www.thread.house/2020/01/git-commit-allow-empty/