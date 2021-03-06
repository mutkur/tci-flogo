---
date: 2016-04-09T16:50:16+02:00
title: Set up your environment
weight: 6
---

Let's get started with the setup of your development environment!

## The Go part
TIBCO Cloud<sup>&trade;</sup> Integration - Flogo<sup>&reg;</sup> is powered by [Project Flogo](https://flogo.io), so when you're developing extensions for TIBCO Cloud<sup>&trade;</sup> Integration - Flogo<sup>&reg;</sup>, the runtime parts are the same as you would create them for Project Flogo. That also means that extensions for Project Flogo will work in TIBCO Cloud<sup>&trade;</sup> Integration - Flogo<sup>&reg;</sup> and vice versa.

To install the Project Flogo parts you need to:

* First install the [Go programming language](https://golang.org/doc/install). 

{{% notice info %}}
Don't forget to set your `GOPATH` variable and make sure that `$GOPATH/bin` is part of your path. (see [here](https://golang.org/doc/code.html#GOPATH) or [here](https://github.com/golang/go/wiki/Setting-GOPATH) for more details)
{{% /notice %}}

* After that, **go get** flogo by running `go get -u github.com/TIBCOSoftware/flogo-cli/...`. This will get you both the CLI tools.
* You should also install **golint** by running `go get -u github.com/golang/lint/golint`
* And finally install the gb build tool (we use that to simplify development and building in Go). You can install that by running `go get github.com/constabulary/gb/...`

{{% notice note %}}
If you want to update the CLI tools, you can run `go get -u github.com/TIBCOSoftware/flogo-cli/...` to get the latest version. 
{{% /notice %}}

Assuming that you want to test your extensions, and as a good developer you really should, you'll need a few extra packages:

* [flogo-lib](https://github.com/TIBCOSoftware/flogo-lib) contains the api and core libraries that are used to create and extend the Flogo Engine. You can install it by running `go get -u github.com/TIBCOSoftware/flogo-lib/...`
* [test](https://github.com/TIBCOSoftware/flogo-contrib/tree/master/action/flow/test) is a simple mechanism to test the Go parts of your extensions. You can install it by running `go get github.com/TIBCOSoftware/flogo-contrib/action/flow/test`
* [Testify](https://github.com/stretchr/testify) which is a toolkit with common assertions and mocks that plays nicely with the standard library. You can install it by running `go get github.com/stretchr/testify/assert`

{{% notice tip %}}
If you've installed Go and want to run all the **go get** commands in one go you can copy/paste the below script
```
go get -u github.com/TIBCOSoftware/flogo-cli/...
go get -u github.com/golang/lint/golint
go get github.com/constabulary/gb/...
go get -u github.com/TIBCOSoftware/flogo-lib/...
go get github.com/TIBCOSoftware/flogo-contrib/action/flow/test
go get github.com/stretchr/testify/assert
```
{{% /notice %}}

## The TypeScript part
The user interface for your activities can either be generated from the **activity.json** files of your extension, or you have the ability to enhance them with a bit of TypeScript.

{{% notice tip %}}
The latest release of the SDK can be found in the **releases** section of the [repository] (https://github.com/TIBCOSoftware/tci-flogo/releases).
{{% /notice %}}


## The Tooling Part

The [Tooling](https://github.com/TIBCOSoftware/tci-flogo/blob/master/tools/readme.md) helps the user to generate a project scaffolding code for the User interface and then the user can proceed with adding the runtime GOLANG code incrementally. The tooling is built as a docker image which is downloadable from the [releases section](https://github.com/TIBCOSoftware/tci-flogo/releases) of this Github repository for individual releases. The Docker image contains both the User Interface and the Run Time SDK and the tooling command line. 

The tooling currently supports :

  1. User Interface Scaffolding code generation.
  1. User Interface code compilation.
  1. User Interface code testing.
{{% notice tip%}}
More Information for the tooling can be found [here](../../tooling/tooling) and on [Github Readme documentaion](https://github.com/TIBCOSoftware/tci-flogo/blob/master/tools/readme.md).
{{% /notice %}}