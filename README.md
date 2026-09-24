# Immich Self-Hosted

A Docker Compose setup for running [Immich](https://immich.app) on your own machine.

Immich is a self-hosted photo and video backup solution with automatic organization, facial recognition, object search, and mobile-first syncing.

## Features

- Self-hosted photo and video library
- Mobile app support for backup and sync
- AI-powered search and metadata extraction
- PostgreSQL-backed storage
- Redis for app services
- Simple Docker deployment

## Stack

This repository includes:

- `immich-server`
- `immich-machine-learning`
- `redis`
- `postgres`

## Requirements

- Docker Engine
- Docker Compose plugin
- Local filesystem access for media and database storage
- Free disk space for library and database files

## Quick Start

1. Copy the example environment file:

```bash
cp .env.example .env
```

2. Edit `.env` to match your system:

```env
UPLOAD_LOCATION=./library
DB_DATA_LOCATION=./postgres
DB_PASSWORD=postgres
IMMICH_VERSION=v3
TZ=Europe/Berlin
```

3. Start the stack:

```bash
docker compose up -d
```

4. Open the app:

```text
http://localhost:2283
```

## Project Files

- `docker-compose.yml` — service definitions
- `.env.example` — default configuration template
- `.env` — local runtime configuration
- `library/` — uploaded media storage
- `postgres/` — PostgreSQL data directory

## Useful Commands

Check running containers:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs -f
```

Stop the stack:

```bash
docker compose down
```

Restart the stack:

```bash
docker compose restart
```

Update the app:

```bash
docker compose pull
docker compose up -d
```

## Backup Recommendations

Back up the following regularly:

- `library/`
- `postgres/`
- `.env`

## Official Links

- [Immich Homepage](https://immich.app)
- [Immich Documentation](https://immich.app/docs)
- [Immich GitHub](https://github.com/immich-app/immich)

## License

This project is a local deployment setup for Immich and is intended for self-hosting use.
