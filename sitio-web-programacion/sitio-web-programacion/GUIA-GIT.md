# Guía para completar la entrega

Este ZIP contiene el código, pero no reemplaza el historial de Git.
Los siguientes comandos generan commits reales en tu computadora.
No subas los archivos mediante “Upload files”: esta consigna pide usar consola.

## 1. Preparar el repositorio existente

Usá Git Bash o la terminal de VS Code. Si ya tenés el repositorio clonado,
abrilo y no vuelvas a clonarlo. Guardá primero cualquier trabajo pendiente.
Si no lo tenés, ejecutá:

```bash
git clone https://github.com/hernannusshn/sitio-web-programacion.git
cd sitio-web-programacion
```

Desde la carpeta del repositorio ejecutá, antes de copiar los archivos nuevos:

```bash
git switch main
git pull --ff-only origin main
git status
git switch -c feature/entrega-github
```

`git status` debe indicar que no hay cambios pendientes antes de crear la rama.
Si la rama feature ya existe, usá otro nombre, por ejemplo feature/entrega-github-2.

## 2. Copiar el contenido del ZIP

Copiá el CONTENIDO de la carpeta `sitio-web-programacion` del ZIP dentro del
repositorio clonado, reemplazando los archivos de igual nombre. No copies la
carpeta contenedora y no borres ni reemplaces la carpeta oculta `.git`.
`index.html` debe quedar al lado de `README.md`, directamente en la raíz.

## 3. Crear tres commits desde consola

Ejecutá cada bloque por separado. Cada commit incluye una parte distinta.

```bash
git add pages/faq.html
git commit -m "feat: agregar acordeon Bootstrap en preguntas frecuentes"
```

```bash
git add index.html images/
git commit -m "feat: ampliar carrusel con dos fotografias locales"
```

```bash
git add styles/styles.css pages/sobre-mi.html pages/proyectos.html pages/contacto.html README.md GUIA-GIT.md .gitignore
git commit -m "style: ajustar responsive y documentar publicacion"
```

Si Git dice “nothing to commit”, revisá que hayas copiado los archivos dentro
del repositorio correcto. No crees commits vacíos para cumplir el mínimo.
Si pide identidad, configurá tu nombre y el email de tu cuenta de GitHub con
`git config user.name "Tu nombre"` y `git config user.email "Tu email"`.

## 4. Subir la rama y fusionar con main

```bash
git push -u origin feature/entrega-github
git switch main
git merge --no-ff feature/entrega-github -m "merge: integrar entrega responsive y componentes Bootstrap"
git push origin main
git log --oneline --graph --all -10
git status
```

Si cambiaste el nombre de la rama, reemplazalo también en estos comandos.
`--no-ff` deja un commit de merge visible. Conservá la rama remota para que
el docente pueda encontrarla. Si hay conflictos, resolvelos antes de continuar.

## 5. Activar Pages y comprobar la publicación

1. En GitHub verificá que el repositorio sea público (debe decir Public).
2. Abrí Settings → Pages.
3. En Source seleccioná Deploy from a branch.
4. Elegí main y / (root), después Save.
5. Esperá a que termine la publicación y abrí el enlace que muestra GitHub.
6. Confirmá que coincida con el enlace previsto del README.
7. Si difiere, corregí el README, quitá la indicación “prevista” cuando esté
   publicado y guardá el cambio desde consola:

```bash
git add README.md
git commit -m "docs: confirmar enlace publicado en GitHub Pages"
git push origin main
```

## 6. Revisar antes de entregar

- Abrí las cinco páginas en 375 px y en escritorio (por ejemplo 1440 px).
- Probá el menú hamburguesa y todos los enlaces internos.
- Recorré las cinco imágenes con Anterior y Siguiente.
- Abrí y cerrá las tres preguntas del acordeón.
- Confirmá que no haya desplazamiento horizontal.
- En GitHub verificá los tres commits y el commit de merge.
- Abrí el sitio publicado desde una ventana privada.

Entregá la URL del repositorio público, no el ZIP:
https://github.com/hernannusshn/sitio-web-programacion
