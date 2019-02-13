# Repository Management

## Software Architectures

### Monolothic

Pros:

* Knowledge Sharing
* Easier dependency management
* Easier version management
* Easier to track breakages across different projects
* Easier to know what team is doing at a glance

Cons:

* Harder to split code ownership
* Harder to define responsibilities
* Monolithic codebases can easily become a mess
  * No strong conventions
  * Can be harder to deploy
* Increased complexity on codebase
* Harder to distinguish responsibility of the codebase

Examples:

* Facebook
  * Only WWW is a monolithic app

Resources:

* [David R. Maclver: Why you should use a single repository for all your company’s projects](https://www.drmaciver.com/2016/10/why-you-should-use-a-single-repository-for-all-your-companys-projects/)
  * It is impossible for your code to get out of sync with itself
  * Any change can be considered and reviewed as a single atomic unit
  * Refactoring to modularity becomes cheap

Questions:

* When should you break down a monolithic app?

### Non-Monolothic

Examples:

* Amazon
  * Lots of data duplication

Common in:

* Microservices \(typically\)
* FaaS / Serverless

#### Microservices

Cons:

* Many repositories
  * Complex
* Poor knowledge sharing

Requires:

* Service Discovery
* Event Bus
  * Pub/Sub

Questions to ask:

* When should you break down a monolothic app into a microservice?
* When does a microservice become a monolithic app?
* If your goal is to keep it as a Single Responsiblity Principle
  * Why not just use a FaaS architecture?

Good for:

* Services that can't exist in a FaaS environment
  * AWS Lambda Limitations
  * * Execution time. AWS has a limit of 15 minutes
    * Storage space
    * Uploads of 50mb zip
    * [https://docs.aws.amazon.com/lambda/latest/dg/limits.html](https://docs.aws.amazon.com/lambda/latest/dg/limits.html)

#### FaaS \(Functions as a Service\) / Serverless

Pros:

* DevOps is not required
* Isolated
* Pay for what you use

Cons:

* Harder debugging
* Increased complexity on infrastructure

Good for:

* Teams with poor devops

## Repository Styles

### Single Repository \(Monorepo\)

Pros:

* Knowledge Sharing
* Common styles and themes
* Easier for team members to switch projects
* Easier to track dependencies between projects
  * Example: I don't have to find the repository where a particular service lives
* Engineers can see work and progress of other people
* Engineers are not siloed

Cons:

* Possibility of a lot of noise/overheads

Examples:

* Angular
* Babel
* Ember
* Jest
* React

Tools:

* For JavaScript/Node.js: [Lerna](https://github.com/lerna/lerna)

Alternatives:

* Consider having fewer repos, but larger

Examples:

* Facebook
  * Actually has many repos, but few \(say less than 10\)
* Google
  * One huge repository built by Google
* [Microsoft's Azure](https://docs.microsoft.com/en-us/azure/devops/learn/devops-at-microsoft/use-git-microsoft)
* Twitter

### Multiple Repositories \(Multirepo\)

Pros:

* Independent teams and styles

Cons:

* Problems with coordination
* Limits knowledge sharing across repositories
* Context switching between work across repositories
* Hard to enforce styles
* Smaller repos, but many
* Engineers can be siloed
* Hard to track depedency management

Common in:

* Microservices
* FaaS / Serverless

Examples:

* Amazon
* Skype

Also known as:

* Polyrepo

## Comparison Matrix \(Software Architectures vs Repository Styles\)

|  | Monolithic | Non Monolithic |
| :--- | :--- | :--- |
| Monorepo | Option A | Option B |
| Multirepo | Option C | Option D |

### A: Monolithic and Monorepo

Pros:

* Knowledge sharing

### B: Non Monolithic and Monorepo

### C: Monolithic and Multirepo

### D: Non Monolithic and Multirepo

