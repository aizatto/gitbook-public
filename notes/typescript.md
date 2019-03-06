# TypeScript

Useful for preventing me from pushing the quick hacks I'm trying to commit in JavaScript.

## Compiler Options

[https://www.typescriptlang.org/docs/handbook/compiler-options.html](https://www.typescriptlang.org/docs/handbook/compiler-options.html)

Enable:

* `declaration: true` when you want to share a Typescript code across modules
* `jsx: react` when you want to share a React component across modules

### Sharing between models

Enable in your compiler option:

* `declaration: true` 
* `jsx: react` 

## Typing

* [https://www.sitepen.com/blog/typescript-cheat-sheet](https://www.sitepen.com/blog/typescript-cheat-sheet)

### function

```typescript
function Render(props: {uri?: string}) {
```

### children

```typescript
interface Props {
  children?: any;
}
```

Recommended [https://github.com/Microsoft/TypeScript/issues/6471\#issuecomment-171456118](https://github.com/Microsoft/TypeScript/issues/6471#issuecomment-171456118)

