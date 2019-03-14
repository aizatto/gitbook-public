# eslint

* [Configuring](https://eslint.org/docs/user-guide/configuring)

```typescript
/* eslint-disable */
// eslint-disable-next-line no-unused-vars
// eslint-disable-line
```

## Typescript

Use [`@typescript-eslint/eslint-plugin`](https://www.npmjs.com/package/@typescript-eslint/eslint-plugin) 

* Package [`eslint-plugin-typescript`](https://www.npmjs.com/package/eslint-plugin-typescript) is deprecated

`Enum` 's don't work well, use

```typescript
/* eslint-disable no-unused-vars */
const enum PackageManager {
  NPM = 'npm',
  YARN = 'yarn',
}
/* eslint-enable no-unused-vars */
```



