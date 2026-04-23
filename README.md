# Guia 01 - InstructoriasBD

API REST desarrollada con Laravel 12 para autenticar usuarios y administrar posts, categorias, autores, libros y prestamos.

## Descripcion

Este proyecto usa Docker, MySQL y JWT para exponer endpoints protegidos y operaciones CRUD sobre los recursos principales.

## Tecnologias

- Laravel 12
- PHP 8.2
- MySQL
- Docker / Laravel Sail
- JWT

## Requisitos

- Docker Desktop
- Composer
- Node.js

## Instalacion y ejecucion

```bash
cp .env.example .env
docker compose up -d
docker compose exec laravel.test composer install
docker compose exec laravel.test php artisan key:generate
docker compose exec laravel.test php artisan jwt:secret --force
docker compose exec laravel.test php artisan migrate
```

## Acceso

- Aplicacion: `http://localhost:8080`
- API: `http://localhost:8080/api`

## Endpoints principales

- Auth: `/api/auth/register`, `/api/auth/login`, `/api/auth/me`, `/api/auth/refresh`, `/api/auth/logout`
- Usuarios: `/api/users`
- Posts: `/api/posts`
- Categorias: `/api/categorias`
- Autores: `/api/autores`
- Libros: `/api/libros`
- Prestamos: `/api/prestamos`

## Nota

Las rutas protegidas usan `auth:api`, por lo que debes enviar `Authorization: Bearer <token>` despues del login.
