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

### 🛑 Stop All Running Containers

```bash
docker compose down
```

## 🔌 Database Connection Details

### 🐬 MySQL

```bash
host: localhost
port: 3306
user: devuser
password: devpass
database: devdb
```

### 🐘 PostgreSQL

```bash
host: localhost
port: 5432
user: devuser
password: devpass
database: devdb
```

### 🍃 MongoDB

```bash
mongodb://root:root@localhost:27017
```

### ⚡ Redis

```bash
redis://localhost:6379
```
