# Lambda

## Invoke

For some reason the last argument isa file. To output to stdout use `/dev/stdout`

```bash
aws lambda invoke --function-name $fn /dev/stdout
```

## Limitations

[https://docs.aws.amazon.com/lambda/latest/dg/limits.html](https://docs.aws.amazon.com/lambda/latest/dg/limits.html)

Maximum of 1000 executions at a time

Execution Time

* Default is 6 seconds
  * Just change it to 30 seconds
* Maximum is 15 minutes
* When using with API Gateway, maximum is 30 seconds
* When making web requests, it is easy to pass 6 second limit

Memory

* Minimum is 128MB; goes up in 64MB increments
* Max is 3GB
* When using with Node.js and Express you have to increase to at least 192MB

Python

* Debugging is a little harder
  * For some reason, output isn’t as clean as debugging using Node.js

Debugging

* API Gateway
* Try command line
  * `sls invoke local —function $f —data $d`
  * `aws lambda invoke —function-name $f —post`

## Prototype Projects

* [URL Shortener](https://github.com/aizatto/url-shortener/)
* [Serverless Prototypes](https://github.com/aizatto/serverless-prototypes)
* [build.my](https://build.my/) or [https://github.com/aizatto/build.my](https://github.com/aizatto/build.my)

