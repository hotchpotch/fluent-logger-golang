fluent-logger-golang
====

[![Build Status](https://travis-ci.org/t-k/fluent-logger-golang.png?branch=master)](https://travis-ci.org/t-k/fluent-logger-golang)

## A structured event logger for Fluentd (Golang)

## How to install

```
go get github.com/t-k/fluent-logger-golang
```

## Usage

Install the package with `go get` and use `import` to include it in your project.

```
import "github.com/t-k/fluent-logger-golang"
```

##Example

```go
package main

import (
  "github.com/t-k/fluent-logger-golang"
  "fmt"
)

func main() {
  logger := fluent.New(fluent.Config{})
  err := logger.Connect()
  if err != nil {
    fmt.Println(err)
  }
  defer logger.Close()
  tag := "myapp.access"
  message := "testing"
  logger.Post(tag, message)
}
```
## Setting Config Values

```go
f := fluent.New(gelf.Config{FluentPort: 80, FluentHost: "example.com"})
```

## Tests
```
go test
```