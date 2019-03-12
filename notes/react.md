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

[https://facebook.github.io/create-react-app/docs/adding-typescript](https://facebook.github.io/create-react-app/docs/adding-typescript)

```text
yarn create react-app my-app --typescript
```

## useEffect with async/await

```javascript
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

## Bootstrap

Use `reactstrap`

* [https://npmcompare.com/compare/react-bootstrap,reactstrap](https://npmcompare.com/compare/react-bootstrap,reactstrap)



