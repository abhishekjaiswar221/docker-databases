# 🐳 Local Development Databases with Docker

This setup allows you to run databases individually using Docker profiles.

## 🚀 Run Database Containers

### 🐬 Run MySQL Container

```bash
docker compose --profile mysql up -d
```

### 🐘 Run PostgreSQL Container

```bash
docker compose --profile postgres up -d
```

### 🍃 Run MongoDB Container

```bash
docker compose --profile mongo up -d
```

### ⚡ Run Redis Container

```bash
docker compose --profile redis up -d
```

### 🗑️ Remove Running Container

```bash
docker compose --profile [profile] down
```

### 🛑 Start/Stop Running Container

```bash
docker compose --profile [profile] start/stop
```

## ⚙️ Configuration

Defaults work with no setup. To override credentials or ports, copy `.env.example` to `.env` and edit it.

Note: Credentials only apply on first start. To change them later, stop the container and delete `data/<db>`.

### 🩺 Check Container Health

```bash
docker compose --profile [profile] ps
```

Admin UIs start only after their database reports healthy.

## 🔌 Database Connection Details

Default credentials shown. Replace with your `.env` values if changed.

### 🐬 MySQL

#### Connection URL

```bash
mysql://devuser:devpass@localhost:3306/devdb
```

#### Connecting via Database Client

```bash
host: localhost
port: 3306
user: devuser
password: devpass
database: devdb
```

#### Connecting via Adminer Web Client

Note: Running on http://localhost:9090

```bash
System: MySQL/MariaDB
server: mysql
user: devuser
password: devpass
database: devdb
```

### 🐘 PostgreSQL

#### Connection URL

```bash
postgresql://devuser:devpass@localhost:5432/devdb
```

Use as `DATABASE_URL` in your app `.env`:

```bash
DATABASE_URL="postgresql://devuser:devpass@localhost:5432/devdb"
```

With Prisma, add `?schema=public`. Local container has no SSL, so if a client forces SSL, add `?sslmode=disable`.

Test with psql:

```bash
psql "postgresql://devuser:devpass@localhost:5432/devdb"
```

Or inside the container (no local psql needed):

```bash
docker exec -it dev-postgres psql -U devuser -d devdb
```

#### Connecting via Database Client

```bash
host: localhost
port: 5432
user: devuser
password: devpass
database: devdb
```

#### Connecting via Adminer Web Client

Note: Running on http://localhost:9091

```bash
System: PostgreSQL
server: postgres
user: devuser
password: devpass
database: devdb
```

### 🍃 MongoDB

#### Connection URL

```bash
mongodb://root:root@localhost:27017/?authSource=admin
```

#### Connecting via Mongo Express Web Client

Note: Running on http://localhost:9092

Basic auth username: admin &
Basic auth password: pass

### ⚡ Redis

#### Connection URL

```bash
redis://localhost:6379
```

#### Connecting via Redis Commander Web Client

Note: Running on http://localhost:9093 (no login)

## 🧯 Troubleshooting

- Port already in use: set another `*_PORT` in `.env`.
- Auth failed after changing credentials: delete `data/<db>` and start again.
- Connecting from another container on the same network: use the service name as host (e.g. `postgres`), not `localhost`.
