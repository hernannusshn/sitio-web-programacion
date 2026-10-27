# HN Programación

Portafolio personal de Hernán. Proyecto de práctica de desarrollo web.

## Enlaces

- Repositorio: https://github.com/hernannusshn/sitio-web-programacion
- Dirección prevista para GitHub Pages: https://hernannusshn.github.io/sitio-web-programacion/

La dirección del sitio debe confirmarse en Settings → Pages después de activar
la publicación. Si el nombre del repositorio cambia, actualizar ambos enlaces.

## Páginas

- Inicio: presentación y carrusel con cinco imágenes.
- Sobre mí: perfil y aprendizaje.
- Proyectos: prácticas de programación.
- FAQ: acordeón de preguntas frecuentes.
- Contacto: información de contacto.

## Tecnologías y diseño

HTML5 semántico, CSS propio, Grid, Flexbox y Bootstrap 5.3.8.
Las cinco páginas incluyen navbar colapsable y las librerías de Bootstrap.
El contenido se organiza en una columna en mobile y dos desde 1024 px.
Se conserva la paleta azul, celeste y gris, con estados hover, focus y active.

## Estructura

- `index.html`: inicio, en la raíz para GitHub Pages.
- `pages/`: cuatro páginas secundarias.
- `styles/style.css`: único CSS propio, generado por Sass.
- `scss/`: código fuente de los estilos, organizado en partials.
- `package.json` y `package-lock.json`: comandos y versión del compilador.
- `images/`: ilustraciones y fotografías locales.

## Uso local

Abrir `index.html` en el navegador. Se necesita conexión para cargar Bootstrap
desde jsDelivr. Las imágenes y el CSS propio usan rutas relativas.

## Publicación

En Settings → Pages seleccionar Deploy from a branch, rama `main`, carpeta
`/ (root)` y guardar. Confirmar la URL publicada y actualizar este README.
Ver `GUIA-GIT.md` para realizar los commits desde consola y mergear la rama.

## Fotografías

Fotografías de referencia de Unsplash, no son fotos personales ni proyectos propios:

- Escritorio: https://images.unsplash.com/photo-1498050108023-c5249f4df085 (identificador de imagen: photo-1498050108023-c5249f4df085).
- Código: https://images.unsplash.com/photo-1515879218367-8466d910aaa4

Las ilustraciones HTML, CSS y Bootstrap pertenecen a la entrega anterior.

## Arquitectura SCSS

El único punto de entrada es `scss/main.scss`. Cada módulo se carga con `@use`
y declara sus propias dependencias; no se utiliza `@import`.

- `utilities/_variables.scss`: colores, tipografía, espaciados y breakpoints.
- `utilities/_mixins.scss`: media queries reutilizables para mobile y desktop.
- `base/_base.scss`: reset y estilos globales.
- `base/_tipografia.scss`: fuente y tamaño del texto.
- `layout/_header.scss`, `_footer.scss`, `_nav.scss`: estructura del sitio.
- `layout/_contenido.scss`, `_escritorio.scss`, `_responsive.scss`: grilla y adaptación.
- `components/`: tarjetas, listas, imágenes, carrusel, botones, estados y acordeón.

Los módulos se cargan en el orden de las reglas originales para conservar
la cascada. Los partials usan variables, nesting y `&:hover`.

### Compilar

Instalar Node.js con npm si todavía no está instalado. Desde la raíz del proyecto:

```bash
npm ci
npm run build
```

Para recompilar automáticamente mientras editás:

```bash
npm run watch
```

Editar solamente los archivos `.scss`. No editar `styles/style.css`: es un
resultado generado y debe subirse al repositorio para que GitHub Pages pueda
servirlo sin instalar Sass. No subir `node_modules`.

### Conservación del diseño

Se mantuvieron el contenido HTML, las clases, Bootstrap por CDN, la navbar,
los colores y las medidas. El único cambio en los cinco HTML es el nombre de
la hoja propia enlazada: `styles.css` pasa a `style.css`, como pide la consigna.
Se eliminó el CSS anterior. No se agregaron estilos inline.

La compilación fue verificada y las declaraciones del resultado coinciden con
el CSS de origen por selector y media query. No se realizó una prueba visual
en navegador en esta entrega; revisar mobile y escritorio antes de entregar.
