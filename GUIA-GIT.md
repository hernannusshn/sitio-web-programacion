# Entrega SCSS: pasos desde consola

Este ZIP contiene el proyecto refactorizado. Los commits y la publicación en tu
GitHub se completan desde tu computadora; el ZIP no contiene un historial Git.
Usá el mismo repositorio del módulo anterior para conservar sus commits.

## 1. Abrir el repositorio

Abrí la carpeta de tu repositorio en VS Code y luego Terminal → Nueva terminal.
Si todavía no lo tenés clonado, ejecutá una sola vez:

```bash
git clone https://github.com/hernannusshn/sitio-web-programacion.git
cd sitio-web-programacion
```

Antes de copiar los archivos nuevos, comprobá que no tengas cambios pendientes:

```bash
git status
git switch main
git pull --ff-only origin main
git switch -c feature/arquitectura-scss
```

Si hay trabajo pendiente, guardalo en un commit antes de continuar.
Si esa rama ya existe, elegí otro nombre y usalo en todos los pasos.

## 2. Copiar la entrega

Copiá el contenido de `sitio-web-programacion` del ZIP sobre la carpeta del
repositorio, reemplazando los archivos con el mismo nombre.
No copies la carpeta contenedora y no reemplaces ni borres `.git`.

IMPORTANTE: borrá `styles/styles.css` del repositorio. Copiar encima no elimina
ese archivo viejo, y la consigna exige retirar la hoja escrita a mano.
La hoja nueva se llama `styles/style.css` y ya está enlazada en los HTML.

## 3. Instalar Sass y compilar

Desde la raíz del repositorio:

```bash
npm ci
npm run build
```

Debe compilar sin errores y generar `styles/style.css`.
Para seguir trabajando, usá `npm run watch` y detenelo con Ctrl+C.

## 4. Registrar tres partes desde consola

Primero, variables, mixins y estilos globales:

```bash
git add scss/utilities scss/base
git commit -m "refactor: extraer variables mixins y estilos base a SCSS"
```

Después, estructura y componentes:

```bash
git add scss/layout scss/components scss/main.scss
git commit -m "refactor: organizar layout y componentes con use y nesting"
```

Por último, compilación, enlaces y documentación:

```bash
git add -A styles
git add index.html pages package.json package-lock.json .gitignore README.md GUIA-GIT.md
git commit -m "build: compilar Sass y reemplazar hoja CSS anterior"
git push -u origin feature/arquitectura-scss
```

No uses “Upload files” de GitHub para reemplazar estos pasos: la consigna pide
commits desde consola. No crees commits vacíos. Si dice “nothing to commit”,
revisá que estés en la carpeta correcta y que hayas copiado los archivos.

## 5. Integrar a main y publicar

```bash
git switch main
git merge --no-ff feature/arquitectura-scss -m "merge: integrar arquitectura SCSS del portafolio"
git push origin main
git log --oneline --graph --all -10
git status
```

Si hay conflictos, resolvelos antes de continuar. Conservá la rama remota.
En GitHub verificá que el repositorio sea público y que Pages siga usando
`main` y `/ (root)`. GitHub Pages usa el CSS compilado que subiste; no compila
SCSS automáticamente con esta configuración.

## 6. Verificar la entrega

- Están las cuatro carpetas obligatorias dentro de `scss/`.
- `main.scss` es el único archivo SCSS sin guion bajo.
- `npm run build` termina sin errores.
- Solo hay una hoja CSS propia: `styles/style.css`.
- El CSS viejo fue eliminado también en GitHub.
- Los cinco HTML mantienen Bootstrap CSS, Bootstrap JS y su navbar.
- El sitio conserva su apariencia en mobile y escritorio.
- Los tres commits aparecen en el historial de `main` después del merge.
- El README muestra el enlace correcto de Pages.

Entregá la URL del repositorio público:
https://github.com/hernannusshn/sitio-web-programacion
