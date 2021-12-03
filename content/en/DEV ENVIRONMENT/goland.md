---
title: "Goland"
linkTitle: "Goland"
date: 2017-01-05
description: >-
  jetbrains' go ide
---

## Installation

Chances are if you have used Jetbrains' PyCharm for Python development you are going to feel right at home using Jetbrains' [Goland](https://www.jetbrains.com/go/) for Go development.&#x20;

You can request a license from IT [here](https://wiki.ccpgames.com/display/C/Central+Home/#). In the meantime, you can install Goland and use the default 30-day trial license by issuing the following commands. The first line downloads a file containing a few opinionated configuration options which we then supply to `winget` as an override to the Goland package's default installation settings.&#x20;

```powershell
Invoke-WebRequest -Uri "https://git.io/JXGyH" -OutFile "goland.config"
winget install Jetbrains.GoLand --override '/S /CONFIG="goland.config"'
# restart shell to reload PATH
```

To launch Goland from PowerShell and open a project in the current directory just type :

&#x20;`goland .`

Now that Goland is up and running we will configure it to use a few additional tools designed to help insure our code conforms to best practices as assessed by the various [linters](https://en.wikipedia.org/wiki/Lint\_\(software\)) that we will encounter a little later in this guide.

## goimports

The [goimports](https://pkg.go.dev/golang.org/x/tools/cmd/goimports) tool automatically formats your source code to comply with Go's rather strict conventions. It also updates your import statements by removing unreferenced packages and attempting to add any missing imports.&#x20;

To configure Goland to run `goimports` whenever a file is saved navigate to the **File** menu and select **Settings**. Then, in the resulting **Settings** window, expand the **Tools** section and select **File Watchers**. Next, click the **+** icon and add **goimports** from the drop-down list. When prompted to configure the tool just accept the defaults.

![configure goimports](../.gitbook/assets/goimports.png)

## golangci-lint

When you submit code to a project based on the eve service template [golangci-lint](https://github.com/golangci/golangci-lint) automatically analyzes it to determine if it conforms to the linters' notion of best practice. _If any issues are found your code will not be merged._ It is important to realize that this type of error does not _necessarily_ indicate your code has a bug; rather, it just means that your code fails to conform to the tool's idea of what constitutes a best practice which _may _indicate a real issue. If you are _certain _that a failing lint check for a certain line of code is wrong or not applicable you can disable it by annotating the line with a specially formed comment. Be aware, however, that more often than not the linters are correct!

To avoid the delays associated with having a remote CI loop inform you there are issues with your code we will install golangci-lint locally so you can run it on demand.

Since golangci-lint is written in Go we can install it using the `go install` command like so :&#x20;

```bash
go install github.com/golangci/golangci-lint/cmd/golangci-lint@latest
```

{% hint style="info" %}
The `go install` command acts a bit like a package manager for Go. By appending a version suffix, in this case `@latest`, we direct go to build a package in module-aware mode, ignoring the go.mod file in the current directory or any parent directory. This is useful for installing executables without affecting the dependencies of the module we are working with.
{% endhint %}

To configure Goland to run golangci-lint whenever a file is saved navigate to the **File** menu and select **Settings**. Then, in the resulting **Settings** dialog, expand the **Tools** section and select **External Tools**. Next, click the **+** icon and provide the following values :&#x20;

| Field             | Value                                                        |
| ----------------- | ------------------------------------------------------------ |
| Name              | `golangci-lint`                                              |
| Program           | `golangci-lint`                                              |
| Arguments         | `run --out-format tab --sort-results --path-prefix $FileDir$` |
| Working Directory | `$FileDir$`                                                  |

![configure golangci-lint](../.gitbook/assets/golangci-lint.png)

To activate the linter navigate to the **Tools** menu, select **External Tools**, and then click **golangci-lint **:&#x20;

![](../.gitbook/assets/run-golangci-lint.png)

Finally, since we will occasionally need to tweak deployment parameters we will add the [terraform](https://www.terraform.io) plugin via the Settings dialogue as well :

![install the terraform plugin](../.gitbook/assets/install-terraform-plugin.png)

## Refactoring

In upcoming sections this guide will often emphasize the importance of refactoring. One reason we recommend Goland is because it offers excellent support for helping you perform sweeping refactors with confidence.

The following operations are so common that we recommended learning the keyboard shortcuts associated with them.

* ****[**Extract variable**](https://blog.jetbrains.com/go/2018/10/26/refactorings-in-goland-extract-and-inline/)

  Being able to easily take magic values and assign them to variables helps you simplify your code.&#x20;

  To accomplish this in Goland highlight a value and use **`ctrl-alt-v`**

* ****[**Extract method or function**](https://www.jetbrains.com/help/go/extract-method.html)

  It is important to be able to take a section of code and extract it into a function or method.

  To accomplish this in Goland select the expression you want to extract and use **`ctrl-alt-m`**

* ****[**Rename**](https://www.jetbrains.com/help/go/rename-refactorings.html)&#x20;

  You should be able to confidently rename symbols across all files in a project.&#x20;

  To rename a symbol in Goland position the caret in the symbol and hit **`shift-f6`**

* ****[**go fmt**](https://www.jetbrains.com/help/go/integration-with-go-tools.html#gofmt)&#x20;

  Go has an opinionated formatter called `go fmt`

  We configured Goland to run this on every file save via the goimports command but you can also run it against a single file using **`ctrl-alt-l`**

* ****[**Run tests**](https://www.jetbrains.com/help/go/performing-tests.html)&#x20;

  You should be able to do any of the above and then quickly re-run your tests to ensure you haven't broken anything.

  In Goland you can run a selected test or test folder using the **`ctrl-shift-f10`** shortcut, but what you should _really _do is [create a comprehensive run configuration](https://www.jetbrains.com/help/go/performing-tests.html#run-with-options) for all of your tests.

* ****[**View function signature**](https://www.jetbrains.com/help/go/viewing-reference-information.html#view-quick-docs)&#x20;

  You should never be unsure how to call a function in Go. Your IDE should readily display its documentation, parameters, what it returns, etc... &#x20;

  In Goland you can type **`ctrl-q`** with the cursor positioned within the function name or **mouse-hover** over a function call to view that function's signature.&#x20;

  For [parameter information](https://www.jetbrains.com/help/go/viewing-reference-information.html#view-parameter-info) specifically type **`ctrl-p`** with the cursor positioned within the function's parenthesis.

* ****[**View function definition**](https://www.jetbrains.com/help/idea/navigating-through-the-source-code.html#go\_to\_declaration)&#x20;

  If it's still not clear what a function does, you should be able to jump to the source code and try and figure it out yourself.&#x20;

  In goland type **`ctrl-b`** with the cursor positioned within the function name or **ctrl-click or middle-click** on the function call to jump to its implementation.

* ****[**Find usages of a symbol**](https://www.jetbrains.com/help/idea/find-highlight-usages.html#find-usages)&#x20;

  Being able to see the context of a function being called can help you better understand that function.&#x20;

  To find usages of a function or other symbol through the current project type **`ctrl-shift-f7`** with the cursor positioned within the symbol's name.

The TL;DR here is that mastering your tools will help you concentrate on the code and reduce context switching.

## Light-edit mode

When you open a file from the command line using the `goland` command _in a folder that does not contain a Jetbrains project_ Goland opens it in a "light weight" editing mode. While this is convenient for making simple edits this mode lacks most of the features you might otherwise expect from a Jetbrains IDE.
