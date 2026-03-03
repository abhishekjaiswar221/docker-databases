# 🐳 Local Development Databases with Docker

This setup allows you to run databases individually using Docker profiles.

## 🚀 Run Database Containers

### 🐬 Run MySQL Container

```bash
docker compose --profile mysql up -d
```

### 🐘 Run PostgreSQL Container

Note: Delete the .gitkeep file in the /data/postgres directory before running this command.

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

### 🛑 Stop Running Container

```bash
docker compose --profile [profile] down
```

## 🔌 Database Connection Details

### 🐬 MySQL

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
host: localhost
port: 3306
user: devuser
password: devpass
database: devdb
```

### 🐘 PostgreSQL

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
host: localhost
port: 5432
user: devuser
password: devpass
database: devdb
```

### 🍃 MongoDB

#### Connecting via Database Client

```bash
mongodb://root:root@localhost:27017
```

#### Connecting via Mongo Express Web Client

Note: Running on http://localhost:9092

Username: admin &
Password: pass

```bash
mongodb://root:root@localhost:27017
```

### ⚡ Redis

#### Connecting via Database Client

```bash
redis://localhost:6379
```

#### Connecting via Redis Commander Web Client

Note: Running on http://localhost:9093

```bash
redis://localhost:6379
```
