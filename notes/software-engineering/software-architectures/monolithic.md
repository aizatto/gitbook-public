# Monolithic

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
* A single release cycle where all components are released togther

Examples:

* Facebook
  * Only WWW is a monolithic app

Questions:

* When should you break down a monolithic app?
* When should you unbundle a monolith?

Resources:

* [David R. Maclver: Why you should use a single repository for all your company’s projects](https://www.drmaciver.com/2016/10/why-you-should-use-a-single-repository-for-all-your-companys-projects/)
  * It is impossible for your code to get out of sync with itself
  * Any change can be considered and reviewed as a single atomic unit
  * Refactoring to modularity becomes cheap

