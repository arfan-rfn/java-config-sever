# Licensing Service

A Spring Boot micro-service for managing software licenses.

## Overview

This service handles CRUD operations for software licenses associated with organizations. It supports internationalization (i18n) with messages in English, Spanish, and Bengali.

## Running the Application

You can run the entire application (including the database) using Docker Compose:

```bash
docker compose up
```

This will start both the service and its dependencies.

Alternatively, you can run the service locally:

```bash
mvn install
mvn spring-boot:run
```

## Database

The service uses Postgres as its database. When running with Docker Compose, the database will be automatically configured with these details:
- Host: localhost
- Port: 5435
- Database: development
- Username: Postgres
- Password: Postgres


The database configuration is managed through Spring Boot properties with the following settings:

- Hibernate DDL auto: none (schema managed manually)
- Show SQL: enabled
- Dialect: PostgreSQL 95
- Driver: org.postgresql.Driver


## Database Schema

The service uses a relational database with the following schema:

```sql
CREATE TABLE IF NOT EXISTS licenses (
    license_id VARCHAR(100) PRIMARY KEY,
    organization_id VARCHAR(100) NOT NULL,
	description VARCHAR(200),
	product_name VARCHAR(100) NOT NULL,
	license_type VARCHAR(100) NOT NULL
);
```

