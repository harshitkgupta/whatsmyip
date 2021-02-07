# whatsmyip
Golang API running as a [Vercel Serverless Function](https://vercel.com/docs/serverless-functions/introduction) which returns your public IP address

![tests](https://github.com/harshitkgupta/whatsmyip/workflows/tests/badge.svg)
<a href='https://github.com/jpoles1/gopherbadger' target='_blank'>![gopherbadger-tag-do-not-edit](https://img.shields.io/badge/Coverage-94%25-brightgreen.svg?longCache=true&style=flat)</a>
![CodeQL](https://github.com/harshitkgupta/whatsmyip/workflows/CodeQL/badge.svg)
<a href='https://goreportcard.com/report/github.com/harshitkgupta/whatsmyip' target='_blank'>![go report](https://goreportcard.com/badge/github.com/harshitkgupta/whatsmyip)</a>

## Links
* [Homepage](https://whatsmyip.harshitkgupta.vercel.app)
* [API](https://whatsmyip.harshitkgupta.vercel.app/api) - supports the following `accept` headers:
    * `application/json`
    * `application/protobuf`
    * defaults to `text/plain`

## Prerequisites
* Required
    * [Go](https://golang.org/)
* Optional
    * [Node.js and npm](https://nodejs.org/en/) for running/deploying with [Vercel](https://vercel.com/)
    * [protoc-gen-go](https://developers.google.com/protocol-buffers/docs/gotutorial) for updating the `protobuf` API contract found [here](./spec/spec.proto)

## Setup
```sh
# Clone the repo and enter directory
git clone git@github.com:harshitkgupta/whatsmyip.git
cd whatsmyip
# Get Vercel and login
npm i -g vercel
vercel login
# Link project to your vercel account
vercel
```

## Usage
If you don't have `make`, you can just run the commands found in the [Makefile](./Makefile) directly
```sh
# Run the webpage & API
make run
# Run tests & benchmarks
make test
# Run the API only
make api
# Update coverage badge
make coverage
# Update protobuf API contract
make protoc
```

If you have issues with `make protoc`:
```sh
go get github.com/golang/protobuf/protoc-gen-go
export PATH=$PATH:$HOME/go/bin
export PATH=$PATH:/usr/local/go/bin
```

## References
* I learned a lot of this from [@codeallthethingz](https://github.com/codeallthethingz)
