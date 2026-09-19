# Olas de Chile - gestión del ecocamp

MVP para gestionar reservas de Olas de Chile Ecocamp en Punta de Lobos.

## Stack
- Cloudflare Workers
- Hono + TypeScript
- Cloudflare D1
- Un único administrador con contraseña hasheada

## Funciones
- Mapa visual de 18 sitios: 7 mirador, 8 bosque, 3 glamping
- Estado por día: libre, ocupado, llegada y salida
- Crear, editar y eliminar reservas
- Planificación, llegadas/salidas y estadísticas en CLP
- Configuración inicial segura en `/setup`
- Código preparado para añadir Google Calendar en fase 2

## Migrar a otra cuenta Cloudflare
1. `npm install`
2. `npx wrangler d1 create olasdechile-db`
3. Pegar el `database_id` en `wrangler.jsonc`
4. `npm run db:migrate:remote`
5. `npm run deploy`
6. Abrir `/setup` y crear el administrador

No hay secretos ligados a la cuenta original. D1 se exporta e importa con Wrangler.
