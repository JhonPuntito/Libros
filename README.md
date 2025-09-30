# Catálogo de libros (con guardado automático en GitHub)

Este repositorio permite gestionar libros y guardar cambios directamente en `books.json` usando GitHub Actions.

## Archivos principales
- `index.html` → página pública de búsqueda.
- `admin.html` → panel de administración con buscador y botón **Guardar en GitHub**.
- `books.json` → base de datos en JSON.
- `.github/workflows/update-books.yml` → workflow que actualiza `books.json`.

## Configuración necesaria
1. Crea un **Personal Access Token (classic)** en GitHub con scope **repo**.
2. Ve a tu repositorio → Settings → Secrets and variables → Actions → New repository secret.
   - Nombre: `GH_TOKEN`
   - Valor: tu token (`ghp_...`).
3. En `admin.html`, reemplaza `USUARIO/REPO` por tu usuario y repo en la línea del fetch.
   - Ejemplo: `"https://api.github.com/repos/jhon/mybooks/dispatches"`

## Flujo de uso
- Abres `admin.html` en GitHub Pages.
- Gestionas tus libros y pulsas **Guardar en GitHub**.
- Se dispara un workflow de GitHub Actions que hace commit automático en `books.json`.
- Tras unos segundos, `index.html` mostrará los cambios.
