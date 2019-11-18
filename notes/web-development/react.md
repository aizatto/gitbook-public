# React

## Glossary

| Name | Definition |  |
| :--- | :--- | :--- |
| [function component](https://reactjs.org/docs/components-and-props.html#function-and-class-components) | React components created with a function\(\) |  |

## Create React App

* TypeScript support

Cons:

* No SEO

### Default

* Change `public/index.html`: `<title>`
* Change `public/mainfest.json`

### Relay

Difficult and heavy

* Requires `relay-compiler`
  * Requires exporting a schema from your graphql endpoint

### SEO

### TypeScript

[https://github.com/sw-yx/react-typescript-cheatsheet](https://github.com/sw-yx/react-typescript-cheatsheet)

#### Creating

```text
yarn create react-app my-app --typescript
```

#### Adding

[https://facebook.github.io/create-react-app/docs/adding-typescript](https://facebook.github.io/create-react-app/docs/adding-typescript)

#### Does Not Support

* No `const enum`

### Directory Structure

```bash
src/components
src/containers
src/routes/EntriesRoute.tsx
```

## useEffect with async/await

{% code title="await-useEffect.tsx" %}
```typescript
function Render() {
  const [data, setData] = useState(null);
  const fetchData = async() => {
    const response = await fetch(`https://www.example.com/`);
    const json = await response.json();
    setData(json);
  };
  useEffect(() => { fetchData() });
  return <div>Test</div>
}
```
{% endcode %}

## useRef\(null\)

Error:

```text
Type error: Cannot assign to 'current' because it is a read-only property.  TS2540
```

From [GitHub comment](https://github.com/DefinitelyTyped/DefinitelyTyped/issues/31065#issuecomment-453841404)

> By default if you create a ref with a `null` default value and specify its generic parameter you're signaling your intent to have React "own" the reference. If you want to be able to mutate a ref that you own you should declare it like so:

Solution:

* Change `useRef<T | null>(null)` to `useRef<T>()`

## Bootstrap

Use `reactstrap`

* [https://npmcompare.com/compare/react-bootstrap,reactstrap](https://npmcompare.com/compare/react-bootstrap,reactstrap)



