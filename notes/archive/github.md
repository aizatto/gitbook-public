# GitHub

See [character-length](https://github.com/aizatto/character-length)

## Notifications

* Add your "other" email to GitHub emails
  * [https://github.com/settings/emails](https://github.com/settings/emails)
* Notifications
  * [https://github.com/settings/notifications](https://github.com/settings/notifications)
    * Automatic watching: disable
    * Automatically watch repositories
    * Change notification custom routing to your "other" email

## Pull Requests

## [Hub](https://github.com/github/hub)

```bash
brew install hub
```

[https://github.com/github/hub/issues/435](https://github.com/github/hub/issues/435)

Disable 2factor temporarily

Open current repository in your browser

```bash
hub browse
```

### Pros

* Searching [https://help.github.com/articles/searching-code/](https://help.github.com/articles/searching-code/)

### Cons

* Doesn't show size of pull requests
  * Makes it easier to quickly gauge which PRs to review
* Pull Requests
  * Code comments don't span multiple lines
  * You cannot comment on files outside modified lines \(within a window\), this is useful for pointing out other errors in the file.
  * Commit Message is not prefilled with 1st comment. You can have Pull Request Templates, but it's not the same. That is a "post" event. we should be able to edit the message before merging.
  * Styling. The Headers \(h1\) make it feel like such a heavy code.
* Comments can't be made on branch comparisons
  * You have to make a PR first
  * [https://github.com/aizatto/git-mv/compare/compare\#diff-c3d57eb88086a04b1e04d06a9b6188e5R3](https://github.com/aizatto/git-mv/compare/compare#diff-c3d57eb88086a04b1e04d06a9b6188e5R3)
* Personal email address can leak into repositories via merges
  * [https://github.com/isaacs/github/issues/95](https://github.com/isaacs/github/issues/95)
* [https://github.com/isaacs/github](https://github.com/isaacs/github)
* [https://github.com/dear-github/dear-github](https://github.com/dear-github/dear-github)
* [https://www.reddit.com/r/golang/comments/71g6c8/proposal\_just\_use\_github\_issue\_21956\_golanggo/](https://www.reddit.com/r/golang/comments/71g6c8/proposal_just_use_github_issue_21956_golanggo/)

### Notes

* Go is on GitHub, but they use Gerrit for code review

### Alternatives

* GitLab
* Upsource
* Phabricator
* Critque \(Used at Google\)

