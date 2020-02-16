# Microservice

Pros:

* Lighter weight deployments

Cons:

* Many repositories
  * Complex
* Poor knowledge sharing
* Orchestration

Requires:

* Service Discovery
* Event Bus
  * Pub/Sub

Good for:

* Services that can't exist in a FaaS environment
  * AWS Lambda Limitations
  * * Execution time. AWS has a limit of 15 minutes
    * Storage space
    * Uploads of 50mb zip
    * [https://docs.aws.amazon.com/lambda/latest/dg/limits.html](https://docs.aws.amazon.com/lambda/latest/dg/limits.html)

When to use microservices?

* A functionality or component that is bottlenecked
  * Would be easier to scale if it was separate
* Reusable functionality across different services
  * Can exist as a library; or micro service
* Isolate small piece of code for:
  * Improved quality
  * Predictable releases
  * Security
* When you want to create a black box
* Reduce transparency
* If it can exist as it’s own product
* Things which can’t exist in a FaaS

Questions to ask:

* When should you bundle a microservice?
* When should you unbundle a microservice?
* When should you break down a monolothic app into a microservice?
* When does a microservice become a monolithic app?
* If your goal is to keep it as a Single Responsiblity Principle
  * Why not just use a FaaS architecture?

