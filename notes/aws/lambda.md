# Lambda

## Invoke

For some reason the last argument isa file. To output to stdout use `/dev/stdout`

```bash
aws lambda invoke --function-name $fn /dev/stdout
```

