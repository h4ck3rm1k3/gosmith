# gosmith
Random Go program generator
Automatically exported from code.google.com/p/gosmith

GoSmith generates random, but legal, Go programs to test Go compilers.

Bugs found to date:

    31 bugs in gc compiler
    18 bugs in gccgo compiler
    5 bugs in llgo compiler (+bug 1, +bug 2, +bug 3, +bug 4)
    3 bugs in the spec were uncovered due to this work 

Usage instructions:
```
# Bootstrap Go implementation:
./make.bash
GOARCH=386 go tool dist bootstrap
GOARCH=arm go tool dist bootstrap
GOARCH=386 go install std
GOARCH=arm go install std
go install -race -a std
go install -a std
# Download binaries:
go get -u code.google.com/p/gosmith/gosmith
go get -u code.google.com/p/go.tools/cmd/ssadump
# Test:
go run driver.go -checkers=amd64,386,arm,exec
```
