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

#### function and object destructuring

```typescript
function Render(props: {uri?: string}) {
```

### React

#### children

```typescript
interface Props {
  children?: any;
}
```

Recommended [https://github.com/Microsoft/TypeScript/issues/6471\#issuecomment-171456118](https://github.com/Microsoft/TypeScript/issues/6471#issuecomment-171456118)

#### useRef

```typescript
export default function UriField() {
  const [uri, setURI] = useState<string | null>(null);
  const inputRef = useRef<HTMLInputElement>(null);
  const onClick = () => {
    if (!inputRef ||
        !inputRef.current) {
      return;
    }

    setURI(inputRef.current.value);
  }

  return (
    <>
      <input ref={inputRef} type="text" />
      <input onClick={onClick} type="submit" value="Submit"/>
    </>
  );
}
```

