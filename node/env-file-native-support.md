# Native support for `.env` files

The `dotenv` package is the most popular way to load environment variables from a `.env` file.

Since version `v20.6.0` comes with native support for `.env` configuration files.

A storage mechanism for key/value vars is handy, but we can also use it to configure the runtime via `NODE_OPTIONS`. This method is a lot easier to manage than long scripts in the package.json file.

Here is a simple example of invoking a node script with the new `--env-file` flag.

```text
# .env
NODE_OPTIONS='--title="Testing Env File'
USER_NAME='Germione Grangere'
```

```javascript
// index.js
console.log(process.title);
console.log(`Hi, ${process.env.USER_NAME} 👋`);
```

```bash
node --env-file=config.env index.js
```

```text
Testing Env File
Hi, Germione Grangere 👋
```

> [!NOTE]
> Since version `21.7`, node add the function `process.loadEnvFile()` is a method to simplify loading environment variables even more. Check out the official documentation for `process.loadEnvFile()`.
