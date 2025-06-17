MIGRATIONS_DIR=db/migrations
SQLC_CONFIG=db/sqlc.yaml
DB_DRIVER=postgres
DB_DSN="postgres://dbuser:dbpass@localhost:5432/dbname?sslmode=disable"

.PHONY: create-migration migrate-up migrate-down status

create-migration:
	goose -dir $(MIGRATIONS_DIR) create $(name) sql

migrate-up:
	goose -dir $(MIGRATIONS_DIR) $(DB_DRIVER) $(DB_DSN) up

migrate-down:
	goose -dir $(MIGRATIONS_DIR) $(DB_DRIVER) $(DB_DSN) down

status:
	goose -dir $(MIGRATIONS_DIR) $(DB_DRIVER) $(DB_DSN) status

sqlc-generate:
	sqlc generate -f $(SQLC_CONFIG)