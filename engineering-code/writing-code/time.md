# Time

I have a preference to use ISO8601 because it's more human readable than unix time. Especially if we are transferring over the web/JSON, it doesn't really matter.

```typescript
2020-03-06T03:05:32.760Z
1583463932760
```

```javascript
new Date().toISOString().length // 24
Date().now().toString().length // 13
```

