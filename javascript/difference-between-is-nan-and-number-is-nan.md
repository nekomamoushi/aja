# Difference Between isNan() and Number.isNan()

`isNaN()` method returns true if a value is Not-a-Number.

`Number.isNaN()` returns true if a number is Not-a-Number.

> NOTE
> `isNaN()` converts the value to a number before testing it.

## Examples

```js
isNaN("Hello"); // true;
```

```js
Number.isNaN("Hello"); // false;
```
