# AppFlowy Cloud — Self-hosted

Despliegue self-hosted de AppFlowy Cloud para reemplazar Notion.

URL: https://appflowy.mystoredigital.cloud
Infra: Oracle Cloud Free Tier (ARM64) via Dokploy + Traefik + Let's Encrypt
Repo gestionado: My-Store-Digital-Team/appflowy

## Servicios

- `nginx` — reverse proxy interno (expuesto a Traefik en :80)
- `postgres` — pgvector/pgvector:pg16
- `redis` — redis:7-alpine
- `minio` — almacenamiento S3-compatible
- `gotrue` — auth (Supabase Auth fork)
- `appflowy_cloud` — backend principal
- `admin_frontend` — panel de admin (/console)
- `appflowy_web` — frontend web (raíz)
- `appflowy_worker` — procesos en background
- `appflowy_search` — búsqueda + indexer

## Configuración

Las variables de entorno se configuran en Dokploy (panel → AppFlowy → Environment).
Nunca commitear `.env` al repo.

Variables requeridas: ver `docker-compose.yml`.

## Admin panel

`https://appflowy.mystoredigital.cloud/console` — login con el `GOTRUE_ADMIN_EMAIL` configurado.
