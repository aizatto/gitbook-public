# Commit Messages

Depending on your version control workflow, this can be either `commit message`s or `pull request`s.

### Sample

```text
fix: prevent more than 12 eggs in a carton

Summary:
Egg cartons only hold a maximum of 12 eggs. The app fataled when there are more than 12 eggs.

We shouldn't store more than 12 eggs in a carton.

We also were able to improve the algorithms to better insert eggs.

Before: 10.7ms
After: 7.3ms


Test Plan:

Run unittest

  phpunit  __tests__

http://example.com/broken-page/

Task: #1
http://example.com/tasks/1
```

**Table Of Contents**

## Commit Messages

Write for clarity.

Write knowing that it will be read later.

Convey intention.

Convey purpose.

The purposes of the commit message is to convey to the reviewer, or someone who has to debug or understand your code in the future, why did we have to write this diff?

## Pros

* Speeds up code review process.
* Becomes most recent up to date documentation.
* Reduces context switching to other systems.
* Helps future maintainers of the repository.
* Extremely helpful for people who have to read alot of code.
* Aids in debugging.

### Commit Message

Commit messages consist of at least three things:

* One Line Summary
* Summary
* Test Plan

Optional \(depending on project\):

* Task
* Additional URLs
* Reviewers
* Reviewed By
* Deployment Process

#### Empty Sample

```text
One Line Summary

Summary:

Test Plan:

Task:
```

### Structure

#### One Line Summary

Contains succinct description of the change.

* Keep this short and sweet. Less than 50 characters.
* Don't make it too generic. For example: "New Unit Test" is bad because it doesn't describe what the unit test does.
* Quick way to reference the diff.
* Use the imperative, present tense: "change" not "changed" nor "changes"
* No dot \(.\) at the end

**Semantic Release**

Adapted from Angular:

Types:

* `build`: Changes that affect the build system or external dependencies \(example scopes: gulp, broccoli, npm\)
* `ci`: Changes to our CI configuration files and scripts \(example scopes: Travis, Circle, BrowserStack, SauceLabs\)
* `config`: Changes to any configurations.
* `docs`: Documentation only changes
* `feat`: A new feature
* `fix`: A bug fix
* `perf`: A code change that improves performance
* `refactor`: A code change that neither fixes a bug nor adds a feature
* `revert`: The summary of the commit that was reverted
* `style`: Changes that do not affect the meaning of the code \(white-space, formatting, missing semi-colons, etc\)
* `test`: Adding missing tests or correcting existing tests

#### Summary

Describe in detail:

* why this diff necessary
* what are the trade offs of your decisions

if its a new feature:

* why do we want to add this feature
* expected result of releasing the feature

if refactoring code

* why are you refactoring the code
* what bash commands you used to find/change the code

if its a bug fix:

* what is expected to happen
* what actually happened
* how the bug was discovered
* how long the bug was live for
* what commit/diff caused the bug
* how the bug was fixed
* severity of the bug
  * people/services effected
  * amount of downtime
  * link to charts displaying severity
  * screenshots of severity

if there is a performance improvement

* give comparison of before/after. For example:
  * how many milliseconds did it take before/after
  * how much memory does it take before/after

#### Test Plan

Test plans are used:

* Reviewers know that you have tested throughly.
* When having to understand old code, you know how to test it thoroughly.

Always try to make the test plan as easy to reproduce as possible. If a test plan is too long, this could potentially be a sign that what you are implementing is too complex.

Include:

* screenshots \(if its a ui change\)
* URIs of the pages effected
* any shell commands that were executed 
* any configuration changes that are needed

#### Additional URLs

Paste any additional relevant URLs, for example URLs to:

* Asana
* GitHub Wikis/Issues
* Google Docs
* Internal Tools
* JIRA
* Kabanize
* Travis
* Wiki Pages

This makes it easy to reference them. Try to use the canonical url when possible.

#### Deployment Process

* How do we deploy this version of the code?
* How can we monitor the deployments?
* What alerts can be received?
* Where can someone receive alerts?

### Example

```text
fix: prevent more than 12 eggs in a carton

Summary:
Egg cartons only hold a maximum of 12 eggs. The app fataled when there are more than 12 eggs.

We shouldn't store more than 12 eggs in a carton.

We also were able to improve the algorithms to better insert eggs.

Before: 10.7ms
After: 7.3ms


Test Plan:

Run unittest

  phpunit  __tests__

http://example.com/broken-page/

Task: #1
http://example.com/tasks/1
```

## Setting Default Commit Messages

### Git

Update `.git/config`, or `~/.gitconfig` file to point to your commit template.

```text
git config --add commit.message FILE
```

## Resources

* [Angular Commit Message Guidelines](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit)
* [Erlang: Writing good commit messages](https://github.com/erlang/otp/wiki/Writing-good-commit-messages)
* [Gerrit Commit message guidelines](https://www.mediawiki.org/wiki/Gerrit/Commit_message_guidelines)
* [Semantic Release](https://github.com/semantic-release/semantic-release)
* [GitHub: Awesome GitHub Issues & PRs Templates](https://github.com/devspace/awesome-github-templates)
* [GitHub: Issue and Pull Request templates](https://github.com/blog/2111-issue-and-pull-request-templates)
* [GitHub: Creating a pull request template for your repository](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/#)
* [GitHub: Search for PULL\_REQUEST\_TEMPLATE](https://github.com/search?utf8=✓&q=in%3Apath+pull_request_template.md&type=Code&ref=searchresults)
* [Open Source Templates](https://www.talater.com/open-source-templates/#/)
* [Kernel Newbies: Patch Philosophy](https://kernelnewbies.org/PatchPhilosophy)
* [https://github.com/RomuloOliveira/commit-messages-guide](https://github.com/RomuloOliveira/commit-messages-guide)

### Angular

* [Angular Commit Message Guidelines](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit)
* [GitHub: PULL\_REQUEST\_TEMPLATE.md](https://github.com/angular/angular/blob/d8d21c77d517f56854c8eb8397b3598861da1e5d/.github/PULL_REQUEST_TEMPLATE.md)

Types:

* `build`: Changes that affect the build system or external dependencies \(example scopes: gulp, broccoli, npm\)
* `ci`: Changes to our CI configuration files and scripts \(example scopes: Travis, Circle, BrowserStack, SauceLabs\)
* `docs`: Documentation only changes
* `feat`: A new feature
* `fix`: A bug fix
* `perf`: A code change that improves performance
* `refactor`: A code change that neither fixes a bug nor adds a feature
* `revert`: The summary of the commit that was reverted
* `style`: Changes that do not affect the meaning of the code \(white-space, formatting, missing semi-colons, etc\)
* `test`: Adding missing tests or correcting existing tests

#### [Samples](https://github.com/angular/angular/commits/master):

* `docs: correct grammar in CONTRIBUTING.md`
* `fix(animations): do not delay style() values before a stagger() runs`
* `fix(aio): build scripts-js before creating a new docker image for t`
* `ci: add npm postinstall back to the lint step so node_modules doesn't`
* `docs: fix spelling of case variants in naming.md`
* `test(compiler): add a test for components not part of any NgModule`
* `build(aio): boilerplate wont be removed by default now`
* `fix(aio): Typo in Setup Anatomy documentation page`
* `docs(aio): fix typo`
* `docs(aio): animations typos fixed`
* `refactor: remove unused imports of the deprecated Renderer`

