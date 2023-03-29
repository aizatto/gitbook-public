# Microservice

Pros:

* Lighter weight deployments
* Can mix usage different programming languages

Cons:

* Many repositories
  * Complex
* Poor knowledge sharing
* Orchestration
  * Understanding orchestration across multiple services/repositories is difficult, especially when thing are inconsistent
* Exchanging ownership
  * Imagine all members of a team leaves, who manages ownership?
* Each team needs to know devops \(to a certain extent\)

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
* Migrating a serivce to a different programming language
  * Migrating bits and pieces

When should you use microservices?

* A functionality or component that is bottlenecked
  * Would be easier to scale if it was separate
* Reusable functionality across different services
  * Can exist as a library; or micro service
* Isolate small piece of code for:
  * Improved quality
  * Predictable/different release cycles
  * Security
* When you want to create a black box
* Reduce transparency
* If it can exist as it’s own product
* Things which can’t exist in a FaaS

When should you not use a microservice?

* When you have a small team

Questions to ask:

* When should you bundle a microservice?
* When should you unbundle a microservice?
* When should you break down a monolothic app into a microservice?
* When does a microservice become a monolithic app?
* If your goal is to keep it as a Single Responsiblity Principle
  * Why not just use a FaaS architecture?

Resources:

* [Susan Fowler: Production-Ready Microservices](https://amzn.to/2tdH6OA)

