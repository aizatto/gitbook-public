# Software Architectures

## Monolothic

Notes:

* A company may have more than one monolith
* A monolith means a big heavy app

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
* When should you unbundle a monolith?

## Non-Monolothic

Examples:

* Amazon
  * Lots of data duplication

Common in:

* Microservices \(typically\)
* FaaS / Serverless

### FaaS \(Functions as a Service\) / Serverless

Pros:

* DevOps is not required
* Reduce security footprint
* Isolated
* Pay for what you use

Cons:

* Harder debugging
* Increased complexity on infrastructure

Good for:

* Teams with poor devops

When to use FaaS?

* Unpredictable demands
  * Competing faaa products \(Ec2\) can leveraged auto scaling
* Small work loads that don’t require an always on machine
* Isolated processes

Examples:

* Low traffic url shortener [https://github.com/aizatto/url-shortener/](https://github.com/aizatto/url-shortener/)

