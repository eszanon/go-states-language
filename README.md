## go-states-language
[![TravisCI Build Status](https://travis-ci.org/eszanon/go-states-language?branch=master)](https://travis-ci.org/eszanon/go-states-language)
<!-- [![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/eofqkk271yjd3s3g?svg=true)](https://ci.appveyor.com/project/eszanon/go-states-language) -->
[![GoDoc](https://godoc.org/github.com/eszanon/go-states-language?status.svg)](https://godoc.org/github.com/eszanon/go-states-language)
[![Go Report Card](https://goreportcard.com/badge/github.com/eszanon/go-states-language?branch=master)](https://goreportcard.com/report/github.com/eszanon/go-states-language) 
<!--[![Go Cover](http://gocover.io/_badge/github.com/eszanon/go-states-language)](http://gocover.io/github.com/eszanon/go-states-language)-->

### Installation

    go get -u github.com/eszanon/go-states-language


## Example
```go
package main

import (
	"flag"
	"fmt"
	"os"

	"gitlab.com/lumminy/pocs/go-states-language/pkg/workflow"
)

func main() {

	jsonFile := flag.String("f", "", "JSON-based Amazon States Language file location")
	flag.Parse()

	if *jsonFile == "" {
		fmt.Println("Invalid JSON-based Amazon States Language file")
		os.Exit(1)
	}

	flow, err := workflow.Validate(jsonFile)
	if err != nil {
		fmt.Println("Workflow not valid. See errors: ", err.Error())
		os.Exit(1)
	}

	fmt.Println("The workflow is valid.")
	fmt.Printf("flow: %#v", flow)

}


```

Read the [documentation](https://godoc.org/github.com/eszanon/go-states-language) for other functions

## Contributing
You know =)