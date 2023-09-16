# BeegoTodo

## Steps [Only API]
- Get Bee Cli Tool
- Generate Project Using `bee api [appname]`
- Generate Model using `bee generate model [modelname] [-fields="name:type"]`
- Generate Controller `bee generate controller [controllerfile]
`
- Add Controller To `routers/router.go`
```go=
package routers

import (
	"github.com/nafeem-evatix/beegotodo/controllers"

	beego "github.com/beego/beego/v2/server/web"
)

func init() {
	ns := beego.NewNamespace("/v1",
		beego.NSNamespace("/todo",
			beego.NSInclude(
				&controllers.TodoController{},
			),
		),
	)

	beego.AddNamespace(ns)
}
```
- Run `bee run -downdoc=true -gendoc=true` this will run and generate and serve API Documentation
- Go to `localhost:8080/swagger` use to do CRUD Operations

![](https://i.imgur.com/ghej4OQ.png)

# Introduction

This is a simple application designed written for a 2-part series on [SitePoint](http://www.sitepoint.com), showing developers coming to [Beego](http://beego.me) (and [Go](http://golang.org)) from Dynamic languages, such as *PHP*, *Ruby* and *Python*, how to get up and running relatively quickly. 

## Part One

Part one of the series covers the following functionality:

- Installing Beego and the command line tool Bee
- Creating a project
- Actions
- Views / Templates
- Routing
- Request Parameters

## Part Two

Part two of the series will cover the following functionality:

- Integrating a database (SQLite3)
- Models
- Forms
- Validation

It's not meant to be an application which is either elegant or beautiful, nor one which takes the full range of security attack vectors into consideration. It may do that with time, but at least initially, it's a simple, learning repository. 

## Installation

- go get github.com/astaxie/beego/orm

## Acknowledgements

I want to give a special thank you to Bill Kennedy from [Ardan Studios](http://www.ardanstudios.com) for all his help and guidance, during the development of the 2-part series.
