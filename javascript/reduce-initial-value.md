# Reduce Initial value

How many times is the reducer function invoked?

```javascript
const nums = [2, 4, 6];

const reducer = (previous, current) => {
  console.count("invoked");
  return previous + current;
};

nums.reduce(reducer);
```

The console will display:

```text
invoked: 1
invoked: 2
```

The response is 2 times.

Why: Because `initialValue` is not specified, `accumulator` is initialized to the first value in the array, and `callbackFn` starts executing with the second value in the array as `currentValue.`

If we add an initial value:

```javascript
const nums = [2, 4, 6];

const reducer = (previous, current) => {
  console.count("invoked");
  return previous + current;
};

nums.reduce(reducer, 0);
```

The console will display:

```text
invoked: 1
invoked: 2
invoked: 3
```
