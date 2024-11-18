# Mouse Event: button property

The `button` property of the `MouseEvent` tells you which mouse button was clicked.

- _0_: Left mouse button (primary)
- _1_: Middle mouse button (auxiliary, if present)
- _2_: Right mouse button (secondary)

```js
const button = document.querySelector("button");

button.addEventListener("click", (e: MouseEvent) => {
  console.log(e.button);
});
```
