# Watch mode

Since `v18.11.0`, node comes with a watch mode.

You can enable that using `--watch` flag to watch the entry point and any imported module.

To be more granular, `--watch-path` allows you to specify a particular directory that should react to changes.

These flags cannot be combined with `--check`, `--eval`, `--interactive` or when used in `REPL` mode.

```bash
node --watch server.js
```

```bash
node --watch-path=./src --watch-path=./tests server.js
```

> [!NOTE]
> This feature has been stable since the `v20.13.0` release
