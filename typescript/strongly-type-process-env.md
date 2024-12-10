# How To Strongly Type `process.env`

A common problem in TypeScript is that `process.env` doesn't give you autocomplete for the environment variables that actually exist in your system:

```typescript
console.log(process.env.MY_ENV_VARIABLE); // No autocomplete
```

They also end up typed as `string | undefined`, which can be annoying if you're passing them into functions that expect a string:

```typescript
const myFunc = (envVar: string) => {
  console.log(envVar.toUpperCase());
};
myFunc(process.env.MY_ENV_VARIABLE);
```

> [!CAUTION]
> Argument of type 'string | undefined' is not assignable to parameter of type 'string'.
> Type 'undefined' is not assignable to type 'string'.

## Augment The Global Type

You can augment the global type `NodeJS.ProcessEnv` to include your environment variables:

```typescript
// globals.d.ts
namespace NodeJS {
  interface ProcessEnv {
    MY_ENV_VARIABLE: string;
  }
}
```

This relies on declaration merging on the global interface `NodeJS.ProcessEnv`, adding an extra property `MY_ENV_VARIABLE`.

Now, in every file in your project, you'll get autocomplete for `MY_ENV_VARIABLE`, and it'll be typed as a `string`.

```typescript
myFunc(process.env.MY_ENV_VARIABLE); // (property) MY_ENV_VARIABLE: string
```

> [!WARNING]  
> However, this doesn't provide any guarantees that the environment variable actually exists in your system.

This means that it's useful when you have relatively few environment variables, or can't get buy-in to add an extra library for checking them.
