# Difference between `first()`, `take(1)` adn `single()`

All return the first element in an `Observable`.

```javascript
rxjs.of(1, 2, 3).pipe(rxjs.operators.first()); // 1
rxjs.of(1, 2, 3).pipe(rxjs.operators.take(1)); // 1
rxjs.of(1).pipe(rxjs.operators.single()); // 1
```

## `first()` vs `take(1)`

Both of these return the first element in an `Observable` and they even have the same timing as they both complete the result after emitting the element.

The difference is when there are no elements in the input stream. In this case, `first()` throws an `Error`, while `take(1)` closes the `Observable` without any elements.

```javascript
rxjs.of().pipe(rxjs.operators.first()); // EmptyError
rxjs.of().pipe(rxjs.operators.take(1)); // no elements
```

When you are sure that the input `Observable` is not `empty`, it's safer to use `first()` as it will report the empty case as an error. On the other hand, if an empty stream can happen, for example the element for the mouseup events is removed from the DOM, `take(1)` is better.

## `single()`

This operator behaves a bit differently than the other two. It not only throws an `Error` for an empty stream (just like `first()`) but also for one that has more than 1 element.

This also changes when it completes the result `Observable` as it needs to wait for the second element (or the end of the input stream) to know that there is indeed only one element coming in the input.

```javascript
rxjs.of(1).pipe(rxjs.operators.single()); // 1
rxjs.of(1, 2, 3).pipe(rxjs.operators.single()); // Sequence contains more than one element
rxjs.of().pipe(rxjs.operators.single()); // EmptyError
```

The `single()` operator is a safer version of `first()` if you want to make sure that only a single element is emitted in the input `Observable`.
