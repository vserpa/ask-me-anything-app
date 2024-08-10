# ask-me-anything-app
Golang and React Vite Application

## Backend

### Run postgres and pgadmin
```shell
docker compose up
```

### Generate Migrations and SQL Code
This app uses gen.go to generates migrates and code
Needs the database running
```shell
go generate ./...
```

## Lib details

### Migrations

```shell
# install
go install github.com/jackc/tern/v2@latest

# init migration project
tern init ./internal/store/pgstore/migrations

# example: create new migrations
tern new --migrations ./internal/store/pgstore/migrations create_rooms_table
tern new --migrations ./internal/store/pgstore/migrations create_messages_table

# run over wrapper thats load .env (is included in gen.go)
go run cmd/tools/terndotenv/main.go
```

### SQLC
https://sqlc.dev/
```shell
# install
go install github.com/sqlc-dev/sqlc/cmd/sqlc@latest

# run (is included in gen.go)
sqlc generate -f ./internal/store/pgstore/sqlc.yaml
```
