# El Salón — Simulador de Onboarding

Roleplay interactivo para validar aptitudes blandas de candidatos a Customer Success Executive (Onboarding).

## Archivos

- `index.html` — el juego. Login (nombre + email) → 10 mesas (una por aptitud) → envío automático del resultado.
- `admin.html` — panel de administrador. Pide contraseña y muestra la lista de candidatos con su puntaje y el detalle de cada elección.

## Cómo se guardan los datos

Los resultados se guardan en una tabla de Supabase (`roleonb_results`). El candidato solo puede insertar su propio resultado (no puede leer los de nadie más). El panel de admin lee los datos a través de una Edge Function (`roleonb-admin`) protegida por contraseña — la key de Supabase que usa el front no tiene permiso de lectura.

## Contraseña de admin

La contraseña actual es `fudo-onb-2026`, definida en el código de la Edge Function (no está expuesta en ningún archivo de este repo). Para cambiarla, hay que editar y volver a desplegar esa función desde el proyecto de Supabase.

## Aptitudes evaluadas

Comunicación, Empatía, Escucha activa, Resolución de problemas, Negociación, Manejo de objeciones, Orientación al cliente, Adaptabilidad, Trabajo bajo presión y Priorización.

El puntaje que ve el candidato al final es solo un mensaje de agradecimiento — el puntaje real (0-100%) y el detalle de cada elección quedan visibles únicamente en el panel de admin.

## Publicar con GitHub Pages

1. Settings → Pages → Deploy from branch → `main` / `/(root)`.
2. La URL del juego para candidatos: `index.html`.
3. La URL del panel de admin: `admin.html`.
