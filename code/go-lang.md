# Go Lang



* [https://golang.org/](https://golang.org/)
* [https://golang.org/doc/code.html](https://golang.org/doc/code.html)
* [https://golang.org/doc/effective\_go.html](https://golang.org/doc/effective_go.html)
* [https://github.com/golang/go/wiki/Learn](https://github.com/golang/go/wiki/Learn)
* [https://github.com/golang/go/wiki/CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)

## Set up

```bash
brew install go
mkdir -p ~/src/go
ln -s ~/src/go ~/go
```

## Inside .bash\_profile

```bash
[[ -d $HOME/src/go/ ]] && export GOPATH=$HOME/src/go/
```

## Others

```bash
export GOPATH=$(go env GOPATH)
export PATH=$PATH:$(go env GOPATH)/bin
```

## Pros

* `gofmt`

## Cons

* Uses tabs for identation

## Editorconfig

[https://github.com/editorconfig/editorconfig-core-go/blob/master/.editorconfig](https://github.com/editorconfig/editorconfig-core-go/blob/master/.editorconfig)

## GraphQL

[https://github.com/neelance/graphql-go](https://github.com/neelance/graphql-go) [https://github.com/graphql-go/graphql](https://github.com/graphql-go/graphql) [https://github.com/graphql-go/relay](https://github.com/graphql-go/relay)

## length

```go
len("/view/")
```

## Best Practices

[https://talks.golang.org/2013/bestpractices.slide\#1](https://talks.golang.org/2013/bestpractices.slide#1) [https://peter.bourgon.org/go-best-practices-2016/\#development-environment](https://peter.bourgon.org/go-best-practices-2016/#development-environment) [https://medium.com/@benbjohnson/standard-package-layout-7cdbc8391fc1](https://medium.com/@benbjohnson/standard-package-layout-7cdbc8391fc1) [https://devhints.io/go](https://devhints.io/go)

## Examples

### Wiki

[https://golang.org/doc/articles/wiki/](https://golang.org/doc/articles/wiki/) [https://golang.org/doc/articles/wiki/final.go](https://golang.org/doc/articles/wiki/final.go)

