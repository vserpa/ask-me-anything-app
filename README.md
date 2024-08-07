# ask-me-anything-app
Golang and React Vite Application

## Backend

Run database
```shell
docker compose up
```

Migrations

```shell
# install
go install github.com/jackc/tern/v2@latest

# init migration project
tern init ./internal/store/pgstore/migrations

# example: create new migrations
tern new --migrations ./internal/store/pgstore/migrations create_rooms_table
tern new --migrations ./internal/store/pgstore/migrations create_messages_table

# run over wrapper thats load .env
go run cmd/tools/terndotenv/main.go
```
