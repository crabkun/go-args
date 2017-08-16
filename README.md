# go-args
a tool for deserializing of os.Args
## Installation
```bash
go get github.com/crabkun/go-args
```
## Usage
```
package main

import (
	"github.com/crabkun/go-args"
	"fmt"
)

func main(){
	m:=go_args.ReadArgs()
	fmt.Println("-------range argsmap start-------")
	for k,v:=range m{
		fmt.Println(k,*v)
	}
	fmt.Println("-------range argsmap end---------")

	ip,_:=m.GetArg("-ip")
	fmt.Println("ip:",ip)

	port,_:=m.GetArg("-port")
	fmt.Println("port:",port)

	_,v:=m.GetArg("-v")
	fmt.Println("verbose:",v)
}
```
```
D:\GOPATH\src\goargstest> go build main.go
D:\GOPATH\src\goargstest> ./main -ip 127.0.0.1 -port 80 -v
-------range argsmap start-------
-ip 127.0.0.1
-port 80
-v
-------range argsmap end---------

ip: 127.0.0.1
port: 80
verbose: true
```