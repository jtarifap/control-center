# Taridev Control Center - Cero build

Sitio estático (HTML/CSS/JS). No requiere instalación ni build.

## Estructura mínima
- index.html: panel completo (login Supabase + secciones con datos reales).
- Assets adicionales opcionales en ssets/.

## Publicar en Render
1. New > Static Site
2. Conectar repositorio
3. Build Command: dejar vacío
4. Publish Directory: control-center
5. Save y Deploy

## Variables
No se necesitan variables secretas: usa la publishable key de Supabase en el código.
