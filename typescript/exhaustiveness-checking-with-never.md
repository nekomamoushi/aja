# Exhaustive Check with `never`

It is great for exhaustive switch statement.

```typescript
type Bird = { kind: "bird"; legs: number; wings: 2 };
type Dog = { kind: "dog"; legs: number };
type Fish = { kind: "fish"; fins: number };
type Animals = Bird | Dog | Fish;

function animalAppendages(animal: Animal): numbers {
  switch (animal.kind) {
    case "bird":
      return animal.wings + animal.legs;
    case "dog":
      return animal.legs + 1;
    case "fish":
      return animal.fins;
    default:
      // thiis should never happen
      let neverHappens: never = animal;
      return neverHappens;
  }
}
```
