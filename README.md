# Taridev Control Center

Panel de control estático (HTML/CSS/JS) para gestionar clientes, aplicaciones, planes, despliegues, guardrails de IA y auditoría. Se conecta a Supabase mediante su API REST (publishable key).

## Características

- Login con Supabase (email y contraseña).
- Clientes: alta, edición, borrado y relación con aplicaciones.
- Aplicaciones y secciones versionadas desde Supabase.
- Despliegues: descriptor, subdominio, estado, plan y secciones visibles.
- Configuración por despliegue: idiomas, avatares, fondos, prompt y guardrails de IA.
- Auditoría de acciones (altas, cambios, borrados).
- Tema claro/oscuro y diseño responsive.

## Ejecutar en local

No requiere instalación ni build. Abre `index.html` en el navegador o sírvelo con cualquier servidor estático.

## Backend (Supabase)

La conexión se define en `index.html` mediante `AUTH_URL` y `ANON_KEY` (clave publishable). No subas ni incluyas claves privadas ni tokens de servicio. Si cambias de proyecto, sustituye solo esas constantes.

Tablas utilizadas:

- `aplicaciones`
- `secciones_aplicacion`
- `tenants`
- `clientes`
- `despliegues`
- `planes` (o `packages` como alternativa)
- `configuracion_despliegue`
- `auditoria`

Configura políticas RLS adecuadas en Supabase según los roles de la aplicación.

## Publicar en Render

Archivo incluido: `render.yaml`.

1. New > Static Site
2. Conectar repositorio
3. Build Command: dejar vacío
4. Publish Directory: `.`
5. Save y Deploy

## Variables y secretos

No se necesitan variables secretas: usa la publishable key de Supabase en el código. Mantén fuera del repositorio cualquier service role key o secreto de terceros.

## Actualizaciones recientes

- Migración de la demo estática a datos reales cargados desde Supabase.
- CRUD de clientes y gestión de despliegues desde el panel.
- Configuración completa por despliegue, incluyendo guardrails de IA y assets.
- Registro de auditoría de las acciones realizadas.
- Ajuste de despliegue estático en Render (`render.yaml`).
