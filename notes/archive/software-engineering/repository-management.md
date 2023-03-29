# Repository Management

## Single Repository \(Monorepo\)

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

## Multiple Repositories \(Multirepo\)

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

Cons:

* Increased operaitonal complexity and cognitive load

