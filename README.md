# flutter-go-grpc

- [protoファイルでProcedureを定義する｜作ってわかる！ はじめてのgRPC](https://zenn.dev/hsaki/books/golang-grpc-starting/viewer/proto)

```
protoc --go_out=../pkg/grpc --go_opt=paths=source_relative \
--go-grpc_out=../pkg/grpc --go-grpc_opt=paths=source_relative \
	hello.proto

protoc --go_out=. --go-grpc_out=require_unimplemented_servers=false:. ./proto/rock-paper-scissors.proto

protoc --go_out=. --go_opt=paths=source_relative \
  --go-grpc_out=. --go-grpc_opt=paths=source_relative \
  helloworld/helloworld.proto

protoc --go_out=. --go_opt=paths=source_relative \
  --go-grpc_out=. --go-grpc_opt=paths=source_relative \
  hello.proto
> protoc-gen-go: program not found or is not executable
> Please specify a program using absolute path or make sure the program is available in your PATH system variable
> --go_out: protoc-gen-go: Plugin failed with status code 1.
↓
$ go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
$ go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2

protoc --go_out=. --go_opt=paths=source_relative \
--go-grpc_out=. --go-grpc_opt=paths=source_relative \
hello.proto

protoc --go_out=./pkg/grpc \
--go_opt=paths=source_relative \
--go-grpc_out=./pkg/grpc \
--go-grpc_opt=paths=source_relative \
./api/hello.proto
```

# install
```
brew install protobuf
brew upgrade protobuf
```

# version
```
protoc --version
libprotoc 24.2
```