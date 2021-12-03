---
title: "Go"
linkTitle: "Go"
date: 2017-01-05
description: >-
  a modern statically typed language for creating high-performance networked applications
---

{% hint style="info" %}
Go is often referred to as _Golang_ which also happens to be easier to Google!
{% endhint %}

## Why Go?

Go is a modern, statically typed, general purpose programming language developed by Google to create reliable and efficient network applications. It's syntax is similar to C and it attempts to combine the high-performance of a low-level language like C with the productivity and convenience of high-level languages like Python. It features garbage collection, fast build times, type inference, and first-class support for "goroutines", lightweight [coroutines](https://en.wikipedia.org/wiki/Coroutine) that lend themselves to building highly concurrent network services. Go was open-sourced by Google in 2012.

Go is popular because it made a number of design choices intended to make it easy to learn and the systems produced using it easy to maintain. To this end ...

* Go has only 25 keywords and useful systems can be built using just the standard library which itself is performant and capable.&#x20;
* Go compiles very quickly enabling rapid feedback and tight developer iteration loops.
* Go offers a backward compatibility promise. Go's designers have promised that Go code written 5 years ago will still build.
* With respect to testing, benchmarking, linting, and deployment GO'S tooling is both built-in and first class.

In other words, with Go you can write code and when you come back to it a year or two later it will still build and everything will still make sense.

Another compelling reason to choose Go is that, per the working agreement, _**TTC only provides support for projects written in Go**_. While we would love to support Python, C#, and even Elixir (for some of us, especially Elixir!) we simply don't have the time, expertise, and staff to support them, their tooling, their best practices, and their ecosystems.

## Install Go

To install Go launch Windows Terminal and use winget like so :

```
winget install GoLang.Go
# restart shell to reload PATH
```

You often need to restart Windows Terminal after installing a new command line utility so that PowerShell will pick up changes to the `$ENV:PATH` variable. Once Windows Terminal has been restarted execute the following command to insure everything is working as expected :

```
go version
```

If all went well you should see output that looks something like the following :

```
% go version
go version go1.17.3 windows/amd64
```

{% hint style="info" %}
You have access to both system and user environment variables from the command line. Here are a few that often come in handy...



`$ENV:USERPROFILE  Your user profile folder.`

`$ENV:TEMP         Folder for temporary files. `

`$ENV:PATH         List of locations searched for executable files.`

`$PROFILE          Path to script that executes when you open a shell.`
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=446E-r0rXHI" %}
for a quick run-down kick-back and watch 100 seconds of go
{% endembed %}

## Go modules

[Go modules](https://golang.org/ref/mod#introduction) aim to help solve problems related to dependency management, version selection, and reproducible builds.

Adding module support to a project is pretty straightforward. Select any folder as the root of the module and execute `go mod init <modulepath>`

This process generates a `go.mod` file containing the module's path, Go version, and list of its dependencies. The `go.mod` file also often contains a URL indicating where the code for the module is available. This is often a reference to the project's repository on github.com. To learn more about modules [check out the documentation](https://golang.org/doc/modules/gomod-ref).&#x20;

If no `<modulepath>` is specified `go mod init` will infer it based on the the name of the current folder. Here is an example of this process executed from the command line :&#x20;

```
mkdir my-project
cd my-project
go mod init my-project
```

A simple `go.mod` file will look something like this :

```
module my-project

go 1.17
```

The `go` command's built-in documentation provides an overview of all available `go mod` and other `go <subcommand>` subcommands which you can access using `go help` from the command line like so :&#x20;

```
go help mod
go help mod init
```

{% hint style="info" %}
Go 1.11 introduced [module](https://github.com/golang/go/wiki/Modules) support which later became the default in version 1.16. The use of `GOPATH` is no longer recommended.  For more information on how to use GOPATH if you run across it in the wild visit [this page](https://golang.org/doc/gopath\_code#GOPATH).
{% endhint %}

## [Godoc](https://pkg.go.dev/golang.org/x/tools/cmd/godoc)

Another quality of life feature of Go is its [documentation](https://golang.org/doc/). To read Go's documentation locally install the `godoc` command like so :

```
go install golang.org/x/tools/cmd/godoc@latest
```

You can then read the docs locally by running `godoc -http :8000`. When you then browse to [localhost:8000/pkg](http://localhost:8000/pkg) you will see documentation for all packages installed on your system.

## Additional resources

Go has a very large third-party module and tooling ecosystem. For a more or less complete list visit [https://awesome-go.com](https://awesome-go.com).