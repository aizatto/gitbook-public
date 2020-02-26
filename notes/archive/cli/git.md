# git

## Configuration

### `.gitconfig`

From my [.gitconfig](https://github.com/aizatto/dotfiles/blob/master/gitconfig)

* Includes typos.

{% code title=".gitconfig" %}
```text
[color]
  diff = auto
  status = auto
  branch = auto
  ui = true
[alias]
  ci = commit
  cloen = clone
  co = checkout
  chekcout = checkout
  dif = diff
  l = log
  l1 = log -n1 -p
  ll = log -p
  stauts = status
```
{% endcode %}

### Bash

```bash
git config user.name "Aizat Faiz"
git config user.email email@example.com
```

#### Version

Include branch in [shell](https://github.com/aizatto/dotfiles/blob/master/bash/dotfiles_scm_info.sh).

Pros:

* You always know which branch is being worked on.

#### Aliases

From my [.bash\_profile](https://github.com/aizatto/dotfiles/blob/master/bash_profile#L48-L73)

{% code title=".bash\_profile" %}
```bash
alias ga='git add'
alias gb='git branch'
alias gba='git branch -a'
alias gau='git add -u'
alias gca='git commit --amend --no-edit'
alias gci='git commit'
alias gcm='git commit -m'
alias gco='git checkout'
alias gdc='git diff --cached'
alias gd='git diff'
alias gdd='git diff --name-only HEAD^ | cat'
alias gf='git fetch'
alias gfgsr='git fetch && git svn rebase'
alias gl='git log'
alias gl1='git log -n1'
alias gl1p='git log -n1 -p'
alias gll='git log -p'
alias gp='git pull'
alias gpr='git pull --rebase'
alias grc='git rebase --continue'
alias gs='git status'
alias gsi='git submodule init'
alias gsu='git submodule update'
alias gsr='git svn rebase'
alias gsrgf='git svn rebase && git fetch && git svn rebase'
alias gf='git diff-tree --no-commit-id --name-only -r HEAD'
```
{% endcode %}

## Commands

```bash
git diff --name-only
git log --graph
```

Compare diff with another branch, good for flattening:

```bash
git diff master..branchname
git diff branchname..master
git diff master..HEAD
```

Display file changes between revisions:

```bash
git diff --name-only HEAD^
git diff --name-status branchname..develop
git diff --name-only branchname..develop
git diff --name-only HEAD^ | xargs mvim -p # useful for opening in multiple tabs
git diff --name-only --diff-filter=d HEAD^ | xargs mvim -p # Filter to ignore deleted files
```

Which tags include a particular commit:

```bash
git tag --contains 741326a842e8c3d443c2787980f2fe6e079ccb39
```

Delete remote branch

```bash
git push origin :dotfiles
```

## Before Pushing

Squash branches as much as possible

```bash
git rebase -i master..
```

## Best Practices

* [https://www.git-tower.com/learn/git/ebook/en/command-line/appendix/best-practices](https://www.git-tower.com/learn/git/ebook/en/command-line/appendix/best-practices)
* [https://www.git-tower.com/learn/git/ebook/en/command-line/branching-merging/branching-can-change-your-life\#start](https://www.git-tower.com/learn/git/ebook/en/command-line/branching-merging/branching-can-change-your-life#start)
* [https://chriskottom.com/blog/2014/02/a-few-modest-best-practices-for-git/](https://chriskottom.com/blog/2014/02/a-few-modest-best-practices-for-git/)
* [https://services.github.com/on-demand/](https://services.github.com/on-demand/)
* [https://github.com/github/gitignore](https://github.com/github/gitignore)
* [http://githooks.com](http://githooks.com)

## Cons

* No equivalent of `hg copy`

## `--fixup`

* [http://fle.github.io/git-tip-keep-your-branch-clean-with-fixup-and-autosquash.html](http://fle.github.io/git-tip-keep-your-branch-clean-with-fixup-and-autosquash.html)

## GitHub

See [GitHub](../github.md)

## GitLab

* Alot more tools.
  * Time Tracking, Milestones, Weight

### Pros

* Merge Requests
  * You can work on the commit message before merginging.

### Cons

* UI is sparse

## Vim

Install [`vim-fugitive`](https://github.com/tpope/vim-fugitive)

Inside `vim`:

In command mode, will open a browser pointing to the file in GitHub

```text
:Gbrowse
```

This works when lines are highlighted as well.

## Resources

* [Engineering Code: Commit Messages](/engineering-code/commit-messages/)

## Browsers

* [gitk](https://git-scm.com/docs/gitk)
* [Tower](https://www.git-tower.com)
* [SourceTree](https://www.sourcetreeapp.com)

### IDEs

* [WebStorm](https://www.jetbrains.com/webstorm/) \(paid\)

