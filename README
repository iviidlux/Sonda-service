# SONDA Backend V4 (AquaSense)

API REST para la nueva base de datos **sondav4** (MySQL). Incluye CRUD completo para 10 entidades y vistas:

- rol, usuario
- instalacion
- catalogo_especies, especies_instaladas, especie_tracking
- procesos
- catalogo_sensores, sensores_instalados
- lectura
- vistas: v_proceso_detalle, v_especie_en_instalacion

## Requisitos
- Node.js 18+
- MySQL 8+

## Setup

```bash
cp .env.example .env
# Edita .env con tus credenciales
mysql -u root -p < db/SONDA_V4.sql
npm install
npm run dev
```

## Endpoints base

- `POST /api/v4/auth/register`
- `POST /api/v4/auth/login` → `{ token }`

Usa el token: `Authorization: Bearer <token>`

### Entidades (CRUD)
`GET /api/v4/<tabla>`  
`GET /api/v4/<tabla>/:<id>`  
`POST /api/v4/<tabla>`  
`PUT /api/v4/<tabla>/:<id>`  
`DELETE /api/v4/<tabla>/:<id>`  

Tablas soportadas:  
`rol, usuario, instalacion, catalogo_especies, especies_instaladas, especie_tracking, procesos, catalogo_sensores, sensores_instalados, lectura`

### Vistas
- `GET /api/v4/views/proceso-detalle`
- `GET /api/v4/views/especie-en-instalacion`

## Notas

- En `usuario` el campo `password_hash` es parte del CRUD genérico. Para crear usuarios vía **/auth/register** usa `password`; este endpoint guardará el hash automáticamente.
- Control de acceso simple con JWT. Puedes usar `requireRoles('super_admin','admin_cuenta')` en rutas críticas.
- El pool MySQL usa `dateStrings: true` para evitar problemas de TZ.
