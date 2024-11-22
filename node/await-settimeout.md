# `setTimeout` using `await`

Since `Node 15`, we have a promised based `setTimeout` (Stable in `Node 16`)

```js
import { setTimeout } from "node:timers/promises";

console.log(new Date().toLocaleTimeString("en")); // => 5:29:19 PM
await setTimeout(1000);
console.log(new Date().toLocaleTimeString("en")); // => 5:29:20 PM
```

When I use it like that, I tend to rename it:

```js
import { setTimeout as sleep } from "node:timers/promises";

await sleep(1000);
```

Anything from timers is covered, including setInterval() and setImmediate().

## What about browsers?

Only “recent” APIs are promise-based, but you can easily wrap setTimeout for promises:

```js
function sleep(delay) {
  return new Promise((resolve) => setTimeout(resolve, delay));
}
```
