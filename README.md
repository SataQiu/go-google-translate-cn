<meta name='keywords' content='google translate, go translate, translator, bangla to english, gopret'>

# go-google-translate-cn

**Do you want to use google translator API?** API is not free anymore. But you can translate 1000 words per day free. And then may be this project can help you to translate unlimited text from one language to another using Google Translator.

**This Library can be used in China.**

# Overview

`go-google-translate-cn` provides a `go` package to translate using Google Translator by parsing HTML.  This library can be used to translate from any language to any other.

In **addition** this library provides a [cli](#cli) to translate text via console.

# Installation

```sh
$ go get -u -v github.com/SataQiu/go-google-translate-cn/...
```

# Usage
```go
package main

import (
	"fmt"
	"log"

	trans "github.com/SataQiu/go-google-translate-cn/pkg"
)

func main() {
	// request struct
	req := &trans.TranslateRequest{
		SourceLang: "en",
		TargetLang: "zh",
		Text:       "I am a student.",
	}
	// translate
	translated, err := trans.Translate(req)
	if err != nil {
		log.Fatalln(err)
	}
	fmt.Println(translated) // 我是学生。
```

# CLI

Command line interface to translate text using command line.

## Install

```sh
$ go get -u -v github.com/SataQiu/go-google-translate-cn/cmd/gopret
$ go install github.com/SataQiu/go-google-translate-cn/cmd/gopret
```

## Usages

```sh
$ gopret translate --sl en --tl zh --text "I am a student."

我是学生。
```
