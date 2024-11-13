# Vitest Globals

`vitest` does not import automatically the globals (contrary to `jest`).

3 solutions:

- add the imports into your test files

  ```js
  import { test } from "vitest";
  ```

- add option `--globals` to the cli command

  ```bash
  vitest --run --reporte verbose --globals
  ```

- add `globals: true` in the vitest config file

  ```js
  import { defineConfig } from "vitest/config";

  export default defineConfig({
    test: {
      globals: true,
    },
  });
  ```
