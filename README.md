# Tienda de Perritos — DevOps

CRUD de productos: frontend estático (Nginx) + backend Node/Express + MySQL 8.

## Ejecución local

```bash
docker compose up -d --build
```

- Frontend: http://localhost
- API:      http://localhost:3001/api/productos
- Health:   http://localhost:3001/api/health

La base de datos se inicializa automáticamente con `db/init.sql` (tabla `productos` + 3 registros de ejemplo). Los datos persisten en el volumen `dbdata`.

Para detener:

```bash
docker compose down        # conserva los datos
docker compose down -v     # elimina tambien el volumen de datos
```

## Estructura

- `frontend/` — HTML/JS estático servido por Nginx, con proxy `/api/` -> backend.
- `backend/`  — API Express con mysql2.
- `db/`       — Imagen MySQL 8 con script de inicializacion.
- `.github/workflows/deploy.yml` — CI/CD: despliegue por SSH a EC2 al hacer push a la rama `deploy`.
