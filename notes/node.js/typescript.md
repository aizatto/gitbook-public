# TypeScript

#### Pros:

* Useful for preventing me from pushing the quick hacks I'm trying to commit in JavaScript.

#### Cons:

* Modules you depend on may not have typescript definitions
  * To avoid typing, you may have to go backwards `const ... = require()`
* Definition hell

## Versioning

| Node | TypeScript Target | Support |
| :--- | :--- | :--- |
| 6.17 | es5 | AWS Lambda Node v6.10 suppor |
|  | es6  |  |
| 8.10-9.11.2 | es2016 |  |
| 8.10-9.11.2 | es2017 | AWS Lambda Node v8.10 support |
|  | es2018 |  |
|  | es2019 |  |

General Rules:

* If you are targeting for web set target to `es5`
* If you targeting for AWS Lambda, set your target to `es2017`
  * `Node.js v8.10` supports `es2017`
* If you are targeting for local and using the latest node, go for `es2018`
  * I'm assuming you can target for `esnext` as well as it wouldn't make sense to write code that the latest Node.js could write...but I could be wrong

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

### Objects

```typescript
interface LRUHashMap  {
  [value: number]: DoublyLinkedList;
}

class LRUHash {
  private hash: LRUHashMap;

  construct() {
    this.hash = {};
  }
}
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

