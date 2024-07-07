cd server
go run server.go
cd ../client
go run client.go



go install google.golang.org/grpc@v1.48.0
go get google.golang.org/protobuf@v1.28.0
go mod init mydemo1
go mod tidy
go mod verify
go clean -modcache
protoc --go_out=. --go-grpc_out=. example.proto
protoc --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative example.proto