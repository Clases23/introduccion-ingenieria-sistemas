
# Notas de Clase: Introducción a HTML y HTML5

## 1. Introducción e Historia de HTML

**¿Qué es HTML?** HTML son las siglas de **HyperText Markup Language** (Lenguaje de Marcado de Hipertexto). Es el lenguaje estándar que se emplea para crear la estructura y el contenido de las páginas web ([HTML - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/HTML#:~:text=HTML%2C%20acr%C3%B3nimo%20en%20ingl%C3%A9s%20de,las%20tecnolog%C3%ADas%20asociadas%20a%20la)). Mediante **etiquetas (tags)** marcamos el texto, imágenes u otros elementos para que el navegador sepa cómo mostrarlos y cómo enlazarlos. HTML es la base de la World Wide Web y su invención fue crucial para el desarrollo de Internet tal como lo conocemos ([HTML - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/HTML#:~:text=im%C3%A1genes%2C%20videos%2C%20juegos%2C%20entre%20otros,1%20%5D%E2%80%8B)).

**Origen de HTML:** Fue creado a finales de la década de 1980 por el científico Tim Berners-Lee en el CERN (Organización Europea para la Investigación Nuclear). En 1989 Berners-Lee propuso un sistema de hipertexto para compartir documentos, y en 1991 publicó “HTML Tags”, el primer borrador que describía 18 etiquetas HTML básicas ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=,las%20necesidades%20del%20desarrollo%20web)). Estas etiquetas originales permitían definir encabezados, párrafos, listas, enlaces, etc., sentando las bases de HTML.

**Evolución de las versiones:**

- **HTML 1.0 (1993):** Primera versión formal de HTML. Era muy sencilla, con solo unas pocas etiquetas básicas para texto e hipervínculos. Permitía estructurar documentos simples. *(Nota: la propuesta inicial de Berners-Lee en 1991 contenía 18 etiquetas, 13 de las cuales sobrevivieron hasta HTML 4.0 ([HTML - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/HTML#:~:text=Tim%20Berners,4%20%5D%E2%80%8B)).)*

- **HTML 2.0 (1995):** Primera estandarización oficial de HTML por IETF. Añadió soporte para **formularios**, imágenes y tablas, ampliando lo que se podía hacer en una página web ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=En%201991%20se%20publica%20formalmente%2C,con%20la%20descripci%C3%B3n%20de%20HTML)) ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=,primer%20est%C3%A1ndar%20oficial%20de%20HTML)).

- **HTML 3.2 (1997):** Ya bajo la tutela del W3C (Consorcio de la Web), se incorporaron más capacidades como **tablas avanzadas**, posibilidad de diseños más complejos (ej. texto alrededor de imágenes) y mejoras en formularios. También se introdujo la capacidad de usar hojas de estilo CSS externamente para mejorar la presentación ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=En%201997%20aparece%2C%20por%20recomendaci%C3%B3n,y%20mejoras%20en%20los%20formularios)).

- **HTML 4.0 (1997) y HTML 4.01 (1999):** Consolidaron muchas características y mejoraron la **accesibilidad**. HTML4.0 introdujo las hojas de estilo en cascada (**CSS**) como forma recomendada de manejar el diseño visual, separándolo del contenido ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=En%201997%20aparece%2C%20por%20recomendaci%C3%B3n,y%20mejoras%20en%20los%20formularios)). La versión 4.01 fue una revisión menor y sería la última gran actualización por muchos años ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=programas%20o%20scripts%20y%20mejoras,en%20los%20formularios)).

- **XHTML (2000):** Una reformulación de HTML 4.01 bajo sintaxis XML más estricta. Buscaba hacer el código más riguroso y bien formado. Aunque XHTML 1.0 se usó bastante, resultaba muy estricto y difícil de mantener; finalmente su adopción fue limitada.

- **HTML5 (2014):** Ante la necesidad de nuevas funciones (video, audio, aplicaciones web ricas) y tras la pausa con XHTML, un grupo llamado WHATWG retomó el desarrollo de HTML en 2004 ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=A%20partir%20de%20entonces%2C%20el,su%20actividad%20estandarizadora%20de%20HTML)). HTML5 es la quinta gran revisión del lenguaje, publicada como estándar en 2014 ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=En%20enero%20de%202008%2C%20se,2)). Añadió **etiquetas semánticas** para una mejor estructura (ej. `<header>`, `<article>`), soporte nativo para **audio y video**, nuevos tipos de entrada de formulario, elementos gráficos (`<canvas>`), entre muchas mejoras modernas. Desde HTML5, el estándar evoluciona de forma *“viva”* con pequeñas actualizaciones (HTML 5.1 en 2016, 5.2 en 2017, etc.) en lugar de versiones enteramente nuevas ([Historia completa del HTML: descubre todo sobre este lenguaje | Tokio School](https://www.tokioschool.com/noticias/historia-lenguaje-html/#:~:text=Desde%20la%20publicaci%C3%B3n%20oficial%20de,un%20modelo%20de%20evoluci%C3%B3n%20incremental)).

En resumen, HTML ha evolucionado de un lenguaje básico de hipertexto a un lenguaje completo y semántico que sirve de cimiento para todas las páginas web. A continuación, nos enfocaremos en **HTML5**, la versión actual, aprendiendo su estructura, etiquetas principales y cómo crear documentos HTML bien formados.

*(**Nota:** Para obtener el máximo provecho, acompañaremos la teoría con **ejemplos prácticos** y ejercicios. ¡Asegúrate de intentar los ejercicios propuestos en cada sección para afianzar tus conocimientos!)*

## 2. HTML5: Estructura y Elementos Básicos

### 2.1 Estructura básica de una página HTML

Todo documento HTML tiene una estructura mínima obligatoria. Esta estructura le indica al navegador que se trata de una página web y define las secciones principales del documento:

- **`<!DOCTYPE html>`** – La primera línea del documento. Declara el *tipo de documento* y en HTML5 se usa simplemente `<!DOCTYPE html>` para indicar que usaremos la versión HTML5. Esto ayuda al navegador a interpretar correctamente el código.

- **`<html>`** – Etiqueta raíz que engloba *todo* el contenido de la página. Debe incluir un atributo `lang` para indicar el idioma del contenido (por ejemplo, `<html lang="es">` para español).

- **`<head>`** – Sección de **cabezera** no visible directamente en la página, donde van metadatos e información para el navegador. Dentro de `<head>` típicamente incluimos:
  - `<meta charset="UTF-8">` – Especifica la codificación de caracteres (UTF-8 es el estándar que permite texto en casi todos los idiomas).
  - `<title>` – Título de la página, que aparece en la pestaña o barra del navegador.
  - Opcionalmente, referencias a **hojas de estilo** (`<link rel="stylesheet" href="styles.css">`), **scripts** (`<script src="app.js">`) y otras metaetiquetas (como `<meta name="viewport" content="width=device-width, initial-scale=1.0">` para diseño responsivo en móviles).

- **`<body>`** – Contiene el **contenido visible** de la página, todo lo que se mostrará al usuario en la ventana del navegador: texto, imágenes, enlaces, formularios, etc. Es la sección principal de contenido.

En HTML5, la estructura básica mínima sería como la del siguiente ejemplo:

```html
<!DOCTYPE html> <!-- Declaramos que el documento es HTML5 -->
<html lang="es"> <!-- Etiqueta raíz del documento con idioma español -->
<head>
  <meta charset="UTF-8"> <!-- Metadatos: codificación de caracteres -->
  <title>Mi Primera Página</title> <!-- Título en la pestaña del navegador -->
</head>
<body>
  <!-- Contenido visible de la página -->
  <h1>¡Hola mundo!</h1>
  <p>Esta es mi primera página web.</p>
</body>
</html>
```

En este código:
- `<!DOCTYPE html>` va al inicio.
- `<html>` abre el documento HTML (se cierra al final con `</html>` aunque no se ve en el fragmento).
- En `<head>` definimos el juego de caracteres y el título.
- En `<body>` colocamos un encabezado (`<h1>`) y un párrafo (`<p>`).

**Ejercicio práctico:** Crea un nuevo archivo llamado `index.html`. Escribe en él la estructura básica mostrada arriba. Dentro del `<body>`, agrega un encabezado con tu nombre como título de la página y un párrafo breve presentándote. Guarda el archivo y ábrelo en un navegador web para verificar que se muestra el título en la pestaña y el contenido en la página.

### 2.2 Etiquetas semánticas de HTML5 (estructura de la página)

HTML5 introdujo varias **etiquetas semánticas** para estructurar mejor el contenido de las páginas. Se llaman *semánticas* porque, en lugar de usar siempre contenedores genéricos como `<div>`, estas etiquetas **describen el significado** del contenido que envuelven (encabezado, navegación, pie de página, etc.). Esto mejora la legibilidad del código y ayuda a los navegadores y motores de búsqueda a entender la organización de la página.

Las principales etiquetas semánticas son:

- **`<header>`** – Define el **encabezado** de una página o de una sección importante. Suele contener el título principal, logos, menús o información introductoria. *Por ejemplo:* en el `<header>` de un sitio podemos tener el logo y el menú principal; en el header de un artículo, el título del artículo y quizás datos del autor.

- **`<nav>`** – Representa una sección de **navegación**. Contiene enlaces de navegación, típicamente un menú con links a las principales secciones del sitio o a partes de la página. *Ejemplo:* un `<nav>` puede contener una lista de enlaces a "Inicio", "Productos", "Contacto", etc.

- **`<main>`** – Indica el **contenido principal** de la página. Debe haber solo **uno** por página. Dentro de `<main>` irá el contenido central que define de qué trata esa página (ej. el artículo principal, los resultados de una búsqueda, etc.).

- **`<section>`** – Define una **sección genérica** del documento, agrupando contenido relacionado por tema. Se usa para dividir el contenido en secciones lógicas, por ejemplo, una sección de "Características" dentro de la página principal, otra sección de "Testimonios", etc. Suele llevar un encabezado propio (`<h2>` o `<h3>`).

- **`<article>`** – Representa un **contenido independiente** y autónomo, que podría ser distribuido o reutilizado por sí solo. Ejemplos típicos: un artículo de blog, una noticia, un post de foro, un comentario de usuario. Un `<article>` normalmente tiene su propio título (`<h2>`, `<h3>`) y contenido que tiene sentido por sí mismo.

- **`<aside>`** – Define contenido **secundario o complementario**, como una barra lateral (sidebar) o un cuadro de información relacionada. El contenido dentro de `<aside>` está *indirectamente relacionado* con el contenido principal. Ejemplo: en una noticia, un `<aside>` podría contener enlaces a otras noticias, o en una página de producto, una lista de productos relacionados.

- **`<footer>`** – Representa el **pie de página** de una sección o de la página completa. Suele incluir información de crédito, derechos de autor, enlaces de contacto, o cualquier información “al final” del contenido principal. Por ejemplo, el footer de un sitio puede tener el copyright, enlaces legales, o un resumen de contacto.

Estas etiquetas semánticas ayudan a estructurar el HTML de forma lógica. Podemos anidar unas dentro de otras según corresponda. Por ejemplo, normalmente `<header>` y `<footer>` van fuera de `<main>` (como cabecera y pie globales de la página), mientras que dentro de `<main>` podemos tener múltiples `<section>` o `<article>` y cada uno podría tener su propio pequeño `<header>` o `<footer>` local.

**Ejemplo de estructura semántica básica:**

```html
<body>
  <header>
    <h1>Mi Sitio Web</h1>
    <p>Bienvenido a mi página personal</p>
  </header>
  
  <nav>
    <ul>
      <li><a href="index.html">Inicio</a></li>
      <li><a href="about.html">Sobre Mí</a></li>
      <li><a href="contact.html">Contacto</a></li>
    </ul>
  </nav>
  
  <main>
    <article>
      <header>
        <h2>Artículo de Ejemplo</h2>
      </header>
      <p>Este es el contenido de un artículo de ejemplo. Aquí iría el texto del artículo.</p>
    </article>
    
    <aside>
      <h3>Información Relacionada</h3>
      <p>Esto es un recuadro lateral con contenido relacionado, como enlaces o anuncios.</p>
    </aside>
  </main>
  
  <footer>
    <p>&copy; 2025 Mi Sitio Web. Todos los derechos reservados.</p>
  </footer>
</body>
```

En este ejemplo completo dentro del `<body>`:
- Hay un `<header>` global con un título `<h1>`.
- Un `<nav>` con una lista `<ul>` de enlaces de navegación (cada link en un `<li>`).
- Un `<main>` que contiene un `<article>` (con su propio `<header>` interno y contenido) y un `<aside>` como barra lateral.
- Al final, un `<footer>` global con un texto de pie de página.

Notemos cómo la estructura es muy clara: se distingue visualmente qué parte es el encabezado, cuál la navegación, cuál el contenido principal, etc. Aunque todos estos elementos por defecto son bloques uno debajo de otro, luego con CSS se pueden diseñar (por ejemplo, colocar el nav a un lado, el aside a la derecha, etc.).

**Ejercicio práctico:** Toma la página básica que creaste en el ejercicio anterior. Ahora estructura su contenido semánticamente:
- Envuelve el título principal en un `<header>` (puedes añadir un subtítulo o descripción si quieres).
- Crea un `<nav>` *debajo* del header con una lista de 2–3 enlaces (pueden apuntar a `#` de momento o a otras páginas que planees crear).
- Coloca el párrafo de presentación dentro de `<main>` y, si tienes varios párrafos, podrías agruparlos en una `<section>`.
- Añade un `<footer>` al final con tu nombre y la fecha.  
Abre la página en el navegador y verifica que, aunque visualmente aún se vea similar (no hay estilo aplicado todavía), el código HTML ahora está mejor organizado y más descriptivo.

### 2.3 Etiquetas de texto y formato (títulos, párrafos, énfasis, etc.)

HTML ofrece diversas etiquetas para dar **formato al texto** y estructurarlo en títulos, párrafos u otros elementos en línea. A continuación, describimos las más comunes:

- **`<h1>` a `<h6>`** – Son las etiquetas de **encabezado/título**. `<h1>` define un título de nivel 1 (el más importante, generalmente único por página), `<h2>` subtítulos de segundo nivel, y así hasta `<h6>` que es el de menor jerarquía. Estos encabezados se usan para títulos de sección y su importancia va disminuyendo del 1 al 6. Por ejemplo, el título principal de un artículo sería `<h1>`, las secciones dentro del artículo usarían `<h2>`, subsecciones `<h3>`, etc. (Es importante no saltarse niveles; comienza con `<h1>` y en orden descendente). Los navegadores suelen mostrar `<h1>` con letra más grande y negrita, `<h2>` un poco más pequeño, etc., pero **no** uses los encabezados solo para hacer texto grande o pequeño – úsalos según la estructura lógica del contenido.

- **`<p>`** – Define un **párrafo** de texto. Es un elemento de bloque (ocupa todo el ancho). Los navegadores le agregan un margen inferior por defecto para separar párrafos. Es la forma estándar de agrupar oraciones o bloques de texto consecutivos.

- **`<span>`** – Etiqueta genérica *en línea* (inline). A diferencia de `<div>` (que es genérico de bloque, veremos `<div>` más adelante), `<span>` se usa para envolver texto o pequeños fragmentos dentro de una línea, sobre todo para aplicar estilos o manipulaciones específicas a ese texto. `<span>` en sí no añade ningún estilo ni significado, simplemente sirve de contenedor. Ejemplo: `<p>Texto normal <span class="resaltado">texto resaltado</span> más texto normal.</p>` – aquí el span podría servir para aplicar color u otro estilo al texto "texto resaltado".

- **`<strong>`** – Indica **énfasis fuerte** en el texto, es decir, marca un texto como importante. Semánticamente, `<strong>` indica que ese fragmento tiene mayor relevancia. Visualmente, los navegadores lo renderizan en **negrita** por defecto.

- **`<em>`** – Indica **énfasis** (énfasis ligero o énfasis verbal). Semánticamente significa que el texto debería leerse con énfasis o entonación. Visualmente, suele aparecer en *cursiva*. (Por convención, `<em>` se ve en cursiva y `<strong>` en negrita. Antes se usaban `<i>` y `<b>` simplemente para italica/negrita sin significado semántico; hoy se prefiere `<em>` y `<strong>` porque aportan significado adicional.)

- **`<br>`** – Inserta un **salto de línea** (break) en medio de un párrafo o línea. Es útil para pasar a la siguiente línea sin iniciar un nuevo párrafo. `<br>` es una etiqueta **vacía** (no tiene cierre, solo `<br>`). Ejemplo: `Hola<br>Mundo` se mostraría en dos líneas separadas dentro del mismo párrafo.

- **`<hr>`** – Inserta una **línea horizontal** (horizontal rule) que normalmente representa una separación temática o cambio de sección dentro del flujo de texto. Por defecto, el navegador dibuja una línea gris horizontal a lo ancho. En HTML5 `<hr>` se interpreta más como un *“corte”* o separación de contenido (por ejemplo un cambio de escena, una transición temática).

- **Otras etiquetas de texto inline útiles:** `<small>` (texto pequeño, para disclaimers o notas al pie, lo muestra más pequeño que el texto normal), `<mark>` (marca texto resaltado, por defecto fondo amarillo como marcador), `<del>` (texto tachado, para indicar contenido eliminado), `<ins>` (texto subrayado para contenido insertado), `<sup>` (superíndice), `<sub>` (subíndice), etc. Estas no las detallaremos por completo, pero saber que existen. Por ejemplo, `<sup>` y `<sub>` son útiles para fórmulas (H<sub>2</sub>O) o notas al pie^1.

Veamos un ejemplo combinando algunas etiquetas de texto:

```html
<h1>Introducción a HTML</h1>
<h2>Subtítulo de la sección</h2>

<p>HTML significa <strong>HyperText Markup Language</strong> (<em>Lenguaje de Marcado de Hipertexto</em>). Es el lenguaje utilizado para crear la estructura de las páginas web.</p>

<p>Esta es una frase con texto normal,<br>y aquí comienza en una nueva línea dentro del mismo párrafo.</p>

<p>Ejemplo de <span style="color: blue;">texto azul en línea</span> usando <code>span</code> con un estilo en línea.</p>

<hr>

<p><small>Nota: Este es un texto menos importante en letra pequeña.</small></p>
```

- El `<h1>` es el título principal de la página, `<h2>` un subtítulo.
- En el primer `<p>`, usamos `<strong>` para resaltar “HyperText Markup Language” (aparece en negrita) y `<em>` para “Lenguaje de Marcado de Hipertexto” (aparece en cursiva). Semánticamente, estamos indicando énfasis en esos términos.
- En el segundo `<p>` se usa `<br>` para forzar un salto de línea dentro del párrafo.
- En el tercer `<p>` mostramos un ejemplo de `<span>` con estilo en línea para colorear texto de azul (usando el atributo `style`, que veremos más adelante; también se usa `<code>` solo para ilustrar cómo se vería un fragmento de código en monoespaciado, aunque no lo explicamos aquí).
- `<hr>` dibuja una línea que separa secciones de contenido.
- Finalmente `<small>` hace que el texto aparezca más pequeño, útil para notas aclaratorias.

**Ejercicio práctico:** Crea un documento HTML (o usa el que ya tienes) y dentro del `<body>` realiza lo siguiente:
- Escribe un `<h1>` con el título de un tema que te guste (por ejemplo "Mis Aficiones").
- Agrega un `<h2>` para una subsección (por ejemplo "Afición 1: El fútbol").
- Escribe varios `<p>` describiendo ese tema. En uno de los párrafos, utiliza `<strong>` para resaltar una palabra importante y `<em>` para enfatizar otra palabra.
- En otro párrafo, usa un `<br>` para dividir una línea.
- Agrega un `<hr>` para separar esa sección de otra.
- Finalmente, añade un párrafo con `<small>` indicando la fuente de la información o una nota al pie. 

Guarda los cambios y abre la página en el navegador para verificar que los encabezados aparecen con diferente tamaño y que el texto en negrita/cursiva se ve correctamente.

### 2.4 Etiquetas multimedia (imágenes, audio, video)

Además de texto, HTML nos permite insertar **contenido multimedia** como imágenes, audio y video de forma nativa.

**Imágenes – `<img>`:** La etiqueta `<img>` embebe una imagen en la página. Es un elemento vacío (no tiene etiqueta de cierre). Sus atributos más importantes son:
- `src`: la fuente o ruta de la imagen (URL o path del archivo de imagen).
- `alt`: texto alternativo que describe la imagen. **Este atributo es obligatorio** para cumplir buenas prácticas de accesibilidad; su contenido se muestra si la imagen no carga y es leído por lectores de pantalla para personas con discapacidad visual.
- `title`: (opcional) texto que aparece como *tooltip* al pasar el cursor sobre la imagen.
- `width` y `height`: (opcionales) para especificar dimensiones en píxeles (o en %). Si no se ponen, la imagen se mostrará en su tamaño original.

Ejemplo de uso de `<img>`:

```html
<img src="logo.png" alt="Logotipo de la empresa" title="Mi Empresa" width="200" height="100">
```

Esto insertará la imagen ubicada en “logo.png” con un tamaño de 200x100 píxeles. Si por alguna razón la imagen no carga, el navegador mostrará el texto "Logotipo de la empresa" (proveniente del alt).

**Audio – `<audio>`:** Nos permite incrustar un reproductor de audio. Puede usarse de forma autónoma o con fuentes anidadas:
- `src`: ruta del archivo de audio (ej. ".mp3", ".ogg").
- `controls`: atributo booleano (no requiere valor) que indica que se deben mostrar controles de reproducción (play, pausa, barra de progreso, volumen). Generalmente siempre se pone para que el usuario pueda controlar el audio.
- Otros atributos: `autoplay` (iniciar automáticamente, *cuidado:* suele ser desactivado por navegadores modernos hasta interacción del usuario), `loop` (repetir en bucle), `muted` (iniciar silenciado).

Ejemplo simple:

```html
<audio src="audio/musica.mp3" controls>Tu navegador no soporta el elemento de audio.</audio>
```

Entre la etiqueta de apertura y cierre de `<audio>` hemos colocado un texto "Tu navegador no soporta..." – ese es el **fallback** (contenido alternativo) que se mostrará solo si el navegador es muy antiguo y no reconoce `<audio>`.

También es común especificar múltiples fuentes dentro de `<audio>` usando `<source>`:
```html
<audio controls>
  <source src="musica.mp3" type="audio/mpeg">
  <source src="musica.ogg" type="audio/ogg">
  Tu navegador no soporta audio HTML5.
</audio>
```
De ese modo, el navegador elegirá el primer formato soportado (aquí MP3 u OGG). Para empezar, con un solo `src` suele bastar, preferiblemente en un formato común (MP3).

**Video – `<video>`:** Similar a `<audio>`, nos permite incrustar video con controles nativos:
- `src`: ruta del video (ej. ".mp4", ".webm").
- `controls`: para mostrar controles de reproducción (play, pausa, etc.).
- `width` y `height`: para definir dimensiones de presentación.
- `poster`: atributo opcional con la ruta a una imagen que se muestra como póster previo antes de reproducir (por defecto, sin poster, aparece un cuadro negro o el primer frame del video).

Ejemplo mínimo:

```html
<video src="videos/ejemplo.mp4" controls width="320" height="240">
  Tu navegador no soporta el elemento de video.
</video>
```

Al igual que con audio, podríamos incluir varias fuentes con `<source>` dentro del `<video>` para distintos formatos (MP4, WebM, Ogg) y también proveer subtítulos con `<track>` (no entraremos en detalle aquí). El texto alternativo dentro de `<video>` cumple función similar: se muestra si el navegador no reconoce la etiqueta.

**Ejemplo combinado de multimedia:**

```html
<h2>Galería Multimedia</h2>

<p>Imagen de muestra:</p>
<img src="images/foto1.jpg" alt="Fotografía de un atardecer" width="400">

<p>Reproductor de audio:</p>
<audio src="media/cancion.mp3" controls>Tu navegador no soporta audio HTML5.</audio>

<p>Reproductor de video:</p>
<video src="media/video.mp4" controls width="480" height="270">
  Tu navegador no soporta video HTML5.
</video>
```

Aquí:
- Insertamos una imagen con alt describiendo la foto.
- Un reproductor de audio con controles.
- Un reproductor de video con tamaño 480x270.

**Ejercicio práctico:** Añade contenido multimedia a una página HTML de ejemplo:
1. Busca una imagen (puede ser un archivo local en la misma carpeta, e.g. "foto.jpg"). Inserta un `<img>` en tu página, proporcionando `src` correcto, `alt` descriptivo y estableciendo un `width` para ajustarla.
2. Añade un `<audio>` con `controls`. Si no tienes un archivo de audio local, puedes intentar usar un enlace a un MP3 público en internet (ten en cuenta que debe ser un enlace directo al archivo .mp3).
3. Añade un `<video>` con `controls`. Si no tienes un video corto, podrías usar igualmente un enlace a un video MP4 público o reutilizar la misma ruta de audio en el src solo para ver que el player aparece (no reproducirá video pero verás el contenedor).
4. Abre la página en tu navegador. ¿Ves la imagen cargada? ¿Aparecen un reproductor de audio con botón de play y un rectángulo de video con controles? Prueba que la imagen muestre el texto alternativo si cambias el nombre del archivo (simulando que no carga). 

### 2.5 Hipervínculos y navegación (la etiqueta `<a>`)

Los **hipervínculos** son la esencia de la web, permitiendo navegar de una página a otra. En HTML, los enlaces se definen con la etiqueta `<a>` (de *anchor*, ancla). Un `<a>` puede enlazar a otra página, a otra sección dentro de la misma página, o a recursos como archivos para descargar, direcciones de email, etc.

Atributos importantes de `<a>`:
- `href` (Hypertext REFerence): indica la URL o ruta del destino del enlace. Ejemplos:
  - `href="https://www.google.com"` – enlace absoluto a un sitio externo.
  - `href="pagina2.html"` – enlace relativo a otra página local del mismo sitio.
  - `href="#seccion1"` – enlace a un ancla dentro de la misma página con `id="seccion1"`.
  - `href="mailto:alguien@ejemplo.com"` – (especial) abre cliente de correo para enviar email.
  - `href="tel:+123456789"` – (especial) enlaces telefónicos en móviles.
- `target`: opcional, especifica dónde abrirá el enlace. Valores comunes:
  - `_self` (por defecto) abre en la misma ventana/pestaña actual.
  - `_blank` abre en una **nueva pestaña**. Útil para enlaces externos, para no sacar al usuario de tu sitio. 
- `title`: texto que aparece al pasar el cursor (tooltip), útil para info adicional.
- (Obsoleto: `name`, antes se usaba para marcar anclas de destino en la misma página, hoy se usa `id` en su lugar.)

Ejemplos de enlaces:

```html
<!-- Enlace externo que abre en nueva pestaña -->
<a href="https://www.wikipedia.org/" target="_blank" title="Ir a Wikipedia">Visitar Wikipedia</a>

<!-- Enlace interno relativo a otra página de nuestro sitio -->
<a href="contacto.html">Página de Contacto</a>

<!-- Enlace a una sección dentro de la misma página -->
<p>Ir a la <a href="#conclusion">conclusión</a> de este artículo.</p>
...
<h2 id="conclusion">Conclusión</h2>
<p>Aquí está la conclusión.</p>
```

- El primer `<a>` apunta a wikipedia.org, con `target="_blank"` para que se abra en otra pestaña. El texto del enlace es "Visitar Wikipedia".
- El segundo `<a>` asume que hay un archivo `contacto.html` en la misma carpeta, y al hacer clic el navegador cargará esa página.
- El tercero muestra cómo saltar dentro de la misma página: `href="#conclusion"` hace referencia a un elemento que tenga `id="conclusion"`. En este caso, más abajo un `<h2>` tiene ese id, por lo que el enlace hará scroll hasta ese encabezado.

Los enlaces pueden contener texto, imágenes u otros elementos. Cualquier cosa dentro de `<a> ... </a>` se convierte en clicable. Por ejemplo, `<a href="foto.jpg"><img src="thumb.jpg" alt="Ver foto en grande"></a>` haría que al clicar la miniatura se abra la imagen grande (comportamiento por defecto: si es misma pestaña, reemplaza la página actual con solo la imagen).

**Ejercicio práctico:** En tu página de ejemplo:
- Añade un menú de navegación (si no lo hiciste en secciones anteriores) usando un `<nav>` con una lista de enlaces `<a>` a diferentes secciones de tu sitio (pueden ser otras páginas HTML que planees crear, como "about.html", "services.html", etc., o simplemente enlaces a "#" por ahora).
- Dentro del contenido, inserta un enlace externo relevante. Por ejemplo, si mencionas HTML en un párrafo, podrías poner un enlace a la página oficial de MDN o W3Schools sobre HTML.
- Crea un enlace interno: añade en tu página un índice o tabla de contenidos al inicio con enlaces que apunten a distintas partes de la misma página (usando `href="#algo"` y poniendo `id="algo"` en las secciones destino).
- Prueba los enlaces en el navegador: asegúrate de que los enlaces internos te llevan a la sección correcta y que los externos abren donde corresponde (_blank para nueva pestaña, etc.).

### 2.6 Listas (no ordenadas, ordenadas y de definición)

Las **listas** nos permiten estructurar contenido en forma de ítems secuenciales. HTML ofrece tres tipos básicos de listas:

- **Listas no ordenadas (`<ul>` – *unordered list*):** Son listas de ítems *sin numeración*, que típicamente aparecen con viñetas (puntos, discos) en lugar de números. Se usan cuando el orden no importa, por ejemplo una lista de características, una lista de recursos, etc.
  
- **Listas ordenadas (`<ol>` – *ordered list*):** Son listas de ítems *numerados* (o con letras, romanos, dependiendo del estilo por defecto o CSS). Se utilizan cuando el orden sí importa, por ejemplo pasos de un procedimiento, ranking, top 10, etc. Por defecto, `<ol>` genera 1., 2., 3., ... para cada ítem.

- **Listas de definición (`<dl>` – *definition list*):** Se utilizan para pares **término – definición**, como glosarios o listas de preguntas y respuestas. Dentro de `<dl>` se usan `<dt>` (definition term) para cada término, y `<dd>` (definition description) para su definición.

En todos los casos, los **elementos de lista** se indican con `<li>` (list item). `<li>` se usa dentro de `<ul>` o `<ol>` para cada elemento. En el caso de `<dl>`, no se usa `<li>`, sino la estructura `<dt>` / `<dd>` como se mencionó.

**Ejemplos:**

```html
<h3>Lista no ordenada de frutas:</h3>
<ul>
  <li>Manzana</li>
  <li>Banana</li>
  <li>Naranja</li>
</ul>

<h3>Lista ordenada de pasos:</h3>
<ol>
  <li>Precalentar el horno a 180°C.</li>
  <li>Mezclar harina, azúcar y huevos.</li>
  <li>Hornear la mezcla durante 45 minutos.</li>
</ol>

<h3>Lista de definiciones - Glosario:</h3>
<dl>
  <dt>HTML</dt>
  <dd>Lenguaje de marcado para la estructura de páginas web.</dd>
  <dt>CSS</dt>
  <dd>Lenguaje de hojas de estilo en cascada para dar estilo a la estructura HTML.</dd>
  <dt>JavaScript</dt>
  <dd>Lenguaje de programación interpretado, ejecutado en el navegador, que permite interactividad.</dd>
</dl>
```

Así se verían:
- La lista `<ul>` mostrará viñetas delante de "Manzana", "Banana", "Naranja".
- La lista `<ol>` mostrará "1. Precalentar...", "2. Mezclar...", "3. Hornear...".
- La lista `<dl>` no tiene viñetas ni números. En su lugar, suele mostrarse el `<dt>` (término) en negrita o alineado a la izquierda, y el `<dd>` (definición) indentado debajo de su término correspondiente.

Notar que para `<ul>` y `<ol>`, cada `<li>` crea un ítem con su viñeta o número. Para `<dl>`, cada par `<dt>` / `<dd>` va asociado; se pueden repetir múltiples `<dt>` seguidos con un `<dd>` común si se quieren sinónimos, etc., pero eso es detalle avanzado.

Las listas pueden **anidarse**: un `<li>` podría contener a su vez otra `<ul>` o `<ol>` para sub-listas (por ejemplo, un punto de la lista tiene su propia lista interna). Basta con indentarlo adecuadamente en el HTML para claridad, pero visualmente aparecerá con viñetas secundarias o numeración secundaria.

**Ejercicio práctico:** Practica con las listas:
- En una página HTML, crea una sección "Tecnologías que quiero aprender" y utiliza una **lista no ordenada** (`<ul>`) para listar 3 o 4 tecnologías (HTML, CSS, Python, etc.).
- Crea también una **lista ordenada** (`<ol>`) con los pasos de tu rutina matutina o los pasos para realizar una receta sencilla.
- Si te sientes con confianza, agrega una **lista de definición** (`<dl>`) para tres términos nuevos que aprendiste en esta clase, dando sus definiciones (por ejemplo: Browser, Servidor, DOM, etc.).
- Abre la página en el navegador y verifica: ¿Aparecen los ítems con viñetas y números como esperabas? Ajusta o agrega `<li>` si olvidaste alguno, y observa cómo el navegador los estructura automáticamente.

### 2.7 Tablas (table, tr, th, td)

Las **tablas** en HTML permiten presentar datos en filas y columnas, similares a una hoja de cálculo o tabla de documento. Aunque para diseño de página ya no se usan (antiguamente se usaban tablas para maquetación, ahora eso se hace con CSS), siguen siendo muy útiles para mostrar datos tabulares: horarios, resultados, listados numéricos, comparativas, etc.

Elementos principales de una tabla HTML:
- **`<table>`** – Contenedor principal de la tabla.
- **`<tr>`** – Table row, representa **una fila de la tabla**. Debe ir dentro de `<table>` (o dentro de `<thead>`, `<tbody>`, `<tfoot>` si se segmenta, pero mantengamos simple: directamente en `<table>` por ahora).
- **`<th>`** – Table header cell, **celda de encabezado**. Representa típicamente una celda de la primera fila o de columna de encabezados. El texto en `<th>` por defecto aparece en *negrita y centrado*. Se usa para títulos de columnas o filas (por ejemplo "Nombre", "Edad").
- **`<td>`** – Table data cell, **celda de datos** normal. Cada `<td>` es una celda con contenido (texto, números, incluso podría contener imágenes o otros elementos). Por defecto aparece como texto normal alineado a la izquierda.

Estructura básica: se crean filas `<tr>` y dentro de cada fila, se ponen celdas `<td>` o `<th>` según corresponda. Todas las filas deberían tener el mismo número de celdas para mantener una tabla consistente (no obligatorio técnicamente, pero visualmente se desalinearía).

Ejemplo de tabla sencilla:

```html
<table border="1">
  <caption>Calificaciones del Examen</caption>
  <tr>
    <th>Estudiante</th>
    <th>Nota</th>
  </tr>
  <tr>
    <td>Ana</td>
    <td>8.5</td>
  </tr>
  <tr>
    <td>Juan</td>
    <td>9.0</td>
  </tr>
  <tr>
    <td>Luis</td>
    <td>7.5</td>
  </tr>
</table>
```

- El atributo `border="1"` en `<table>` no es estrictamente parte de HTML5 (era más de HTML4) y se considera *depreciado* en favor de CSS; sin embargo, lo usamos aquí para que dibuje un borde visible y así podamos apreciar la tabla fácilmente. En producción, normalmente usaríamos CSS (`border:` propiedades) para dar estilo a la tabla.
- `<caption>` es opcional, proporciona un título o pie para la tabla, que algunos navegadores muestran centrado encima de la tabla. En este caso "Calificaciones del Examen".
- La primera fila `<tr>` contiene dos `<th>`: "Estudiante" y "Nota". Estos son los encabezados de las columnas.
- Las filas siguientes contienen `<td>` con los datos correspondientes para cada estudiante y su nota.
- Esta tabla tendría 4 filas (una de encabezados + 3 de datos) y 2 columnas.

Si la abrimos en un navegador, veremos una pequeña tabla con los bordes dibujados:
```
---------------------
| Estudiante | Nota |
---------------------
| Ana        | 8.5  |
| Juan       | 9.0  |
| Luis       | 7.5  |
---------------------
```
(Aproximadamente así, en texto)

**Elementos adicionales (mención breve):** Para tablas más complejas existen `<thead>`, `<tbody>`, `<tfoot>` que permiten separar en HTML la sección de encabezado, cuerpo y pie de la tabla (útil para estilos o para que un encabezado se repita en páginas imprimidas, etc.). También se puede usar colspan o rowspan en `<th>`/`<td>` para combinar celdas horizontal o verticalmente. Pero estos son detalles avanzados; con `<table>, <tr>, <th>, <td>` tienes lo necesario para empezar a crear tablas básicas.

**Ejercicio práctico:** Crea una tabla:
- Por ejemplo, una tabla de "Horario de Clases" con columnas "Día" y "Materia", y filas con los días de la semana y la materia que toca ese día.
- Asegúrate de usar una fila de encabezados con `<th>` (ej: "Día", "Materia") y luego filas de datos con `<td>`.
- Pon `border="1"` en la tabla para ver los bordes mientras practicas.
- Abre la página en el navegador y verifica que la tabla se muestre correctamente alineada en filas y columnas. Intenta añadir una columna extra (ej: "Profesor") asegurándote de agregar tanto un `<th>` en la cabecera como celdas `<td>` en cada fila de datos para esa columna.
- Como desafío adicional, intenta crear otra tabla pequeña, por ejemplo una tabla de 2x2 con cualquier dato, solo para familiarizarte.

### 2.8 Formularios (form, input, textarea, select, button)

Los **formularios** permiten la interacción del usuario con la página, recopilando datos que luego típicamente son enviados a un servidor para ser procesados (registro, login, búsqueda, encuestas, etc.). En HTML, un formulario se define con `<form>` y dentro de él colocamos campos de entrada, botones y controles variados.

**Elemento `<form>`:** es el contenedor del formulario. Atributos importantes:
- `action`: la URL o destino donde se enviarán los datos del formulario al ser enviado. Por ejemplo, `action="procesar.php"` o una URL completa. Si se deja vacío o como `"#"`, no envía a ningún lugar (utilizado a veces para manejar vía JavaScript o en desarrollo).
- `method`: método HTTP de envío, comúnmente `"GET"` o `"POST"`. GET envía los datos anexados a la URL (query string), POST los envía ocultos en el cuerpo de la petición (mejor para datos largos o sensibles).
- (Existen más atributos como `enctype` para tipo de codificación en envíos de archivos, etc., pero en nivel básico podemos no especificarlos salvo que subamos archivos).

Dentro de `<form>...</form>` colocamos **controles de formulario**, principalmente con la etiqueta `<input>` y otras específicas:

- **`<input>`:** Representa un **campo de entrada** corto. Es un elemento vacío (sin cierre separado). El tipo de campo depende del atributo `type`. Hay muchos tipos:
  - `type="text"` – campo de texto de una línea.
  - `type="password"` – campo de texto que oculta los caracteres (para contraseñas).
  - `type="email"` – similar a text, pero para email (los navegadores pueden validar formato y mostrar teclado adecuado en móviles).
  - `type="number"`, `type="date"`, etc. – HTML5 introdujo muchos tipos específicos con comportamientos/validaciones particulares.
  - `type="radio"` – botón de opción (selección única, en grupo con mismos `name`).
  - `type="checkbox"` – casilla de verificación (selección múltiple).
  - `type="submit"` – botón de enviar el formulario. Al hacer clic, por defecto envía el form según `action` y `method`.
  - `type="button"` – botón genérico (no envía nada, a menos que se controle con script).
  - `type="reset"` – botón para resetear los campos a su valor inicial.
  - etc. (range, color, file, search, tel, etc.)

  Atributos clave para `<input>`:
  - `name`: **nombre del campo**, importante para identificar el dato en el servidor (ej. name="usuario"). Sin name, el dato no se envía.
  - `value`: valor inicial del campo (para text, el texto prellenado; para radio/checkbox, el valor que representa; para submit/reset, el texto del botón; etc.).
  - `placeholder`: texto guía que aparece dentro de campos text/varios cuando están vacíos, como sugerencia (ej. "Escribe tu nombre...").
  - `checked`: (solo radio/checkbox) atributo booleano para marcarlo seleccionado por defecto.
  - `required`: atributo booleano para indicar que el campo es obligatorio (HTML5 hará validación sencilla).
  - `min`, `max`, `maxlength`, `pattern`, etc. según tipo de input, controlan validaciones de HTML5.

- **`<label>`:** Etiqueta de texto para un control de formulario. Asociar correctamente etiquetas mejora la usabilidad: al hacer clic en el texto de la etiqueta, se activa/enfoca el campo correspondiente. Para asociar, se utiliza el atributo `for` en `<label>` con el `id` del input correspondiente. Ejemplo: `<label for="email">Email:</label> <input type="email" id="email" name="email">`. Así, "Email:" está ligado al campo email. (También se puede anidar el input dentro del label en HTML5, pero la forma con `for`/`id` es más común.)

- **`<textarea>`:** Campo de texto de **múltiples líneas**. Tiene etiquetas de apertura y cierre. Atributos principales: `name`, `rows` y `cols` (tamaño en filas y columnas visibles; aunque en la práctica el tamaño suele ajustarse con CSS), `placeholder`. Ejemplo: `<textarea name="mensaje" rows="4" cols="50" placeholder="Escribe tu mensaje..."></textarea>`.

- **`<select>`:** Desplegable de selección (lista de opciones). Dentro de `<select>` van múltiples `<option>` representando cada opción:
  - `<option value="valor">Texto Visible</option>`. El atributo `value` es el valor enviado si esa opción es elegida. Si se omite `value`, por defecto se envía el contenido de texto. Puede usarse `selected` en una `<option>` para marcarla por defecto.
  - También existe `<optgroup>` para agrupar opciones bajo subtítulos, pero es detalle adicional.

- **`<button>`:** Etiqueta para un botón clickeable. Puede usarse en lugar de `<input type="submit">` porque `<button type="submit">Enviar</button>` funciona igual, y permite contenido HTML dentro (iconos, etc.). Tipos: `type="submit"`, `type="button"`, `type="reset"` similar a input. Si no se especifica `type`, por defecto en un formulario `<button>` actúa como submit.

**Ejemplo de un formulario completo:**

Imaginemos un formulario de contacto sencillo:

```html
<form action="/enviar_formulario" method="post">
  <!-- Campo de texto para Nombre -->
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre" placeholder="Tu nombre" required>
  <br>
  
  <!-- Campo de texto para Email -->
  <label for="correo">Email:</label>
  <input type="email" id="correo" name="correo" placeholder="correo@ejemplo.com">
  <br>
  
  <!-- Campo de área de texto para Mensaje -->
  <label for="mensaje">Mensaje:</label><br>
  <textarea id="mensaje" name="mensaje" rows="4" cols="40" placeholder="Escribe tu mensaje aquí"></textarea>
  <br>
  
  <!-- Campo de selección de tema de consulta -->
  <label for="tema">Tema:</label>
  <select id="tema" name="tema">
    <option value="soporte">Soporte</option>
    <option value="ventas">Ventas</option>
    <option value="otros" selected>Otros</option>
  </select>
  <br>
  
  <!-- Botones -->
  <button type="submit">Enviar</button>
  <button type="reset">Limpiar</button>
</form>
```

Explicación:
- El `<form>` tiene `action="/enviar_formulario"` (es una URL ficticia; en la práctica aquí iría la ruta al script que procesa los datos) y `method="post"` (convención para enviar datos de formulario).
- Cada campo tiene su `<label>` asociado:
  - "Nombre:" con un `<input type="text" name="nombre" required>` para el nombre (obligatorio).
  - "Email:" con `<input type="email" name="correo">`.
  - "Mensaje:" con un `<textarea name="mensaje">`.
  - "Tema:" con un `<select name="tema">` y varias `<option>` (la opción "Otros" está marcada por defecto con `selected`).
- Tras cada control hemos puesto `<br>` para que cada campo quede en una nueva línea (así los labels y campos se apilan verticalmente para esta demostración simple; en diseño real, podríamos usar CSS para alinearlos).
- Al final hay un botón de enviar (submit) y uno de limpiar (reset).
- Cuando se pulsa "Enviar", el navegador intentará enviar los datos a la URL especificada. (En nuestro ejemplo, no habrá un servidor para procesarlo, así que quizás abra una página inexistente; para pruebas locales, a veces se usa `action="#"` para simplemente recargar la misma página).

En el navegador, este formulario se vería con campos donde el usuario puede tipear texto, seleccionar opciones, etc. El botón "Limpiar" restablece todos los campos a su estado inicial (borrando lo escrito).

**Ejercicio práctico:** Crea un archivo HTML con un formulario de registro de usuario que contenga:
- Campos de texto para "Nombre de usuario" y "Correo electrónico".
- Un campo de contraseña (`<input type="password">`) para "Contraseña".
- Un grupo de radio buttons para "Género" (masculino, femenino, otro) – Recuerda dar el mismo `name` a todos los radio de género (por ej. name="genero") para que solo se pueda seleccionar uno, y valores distintos (`value="M"`, `value="F"`, etc.).
- Varias checkboxes para "Intereses" (por ej. Música, Deporte, Lectura).
- Un menú desplegable `<select>` para "País" con al menos 3 `<option>` (por ej. Colombia, México, España).
- Botón de Enviar y Reset.

No es necesario que el formulario realmente envíe a un servidor (puedes usar `action="#"` y `method="get"` por ejemplo para probar, así cuando le des Enviar verás los datos en la URL). Abre la página y prueba interactuar: marca checkboxes, elige opciones, y presiona Enviar (si usaste GET a "#", verás en la barra de direcciones algo como `?nombreUsuario=...&correo=...` con los datos que llenaste). Asegúrate de que los labels estén vinculados (clickeando el texto de un label debería activar el input correspondiente, especialmente útil para radios y checkboxes).

### 2.9 Atributos comunes en HTML (class, id, style, alt, title, etc.)

Las etiquetas HTML suelen aceptar **atributos** que proporcionan información adicional o configuran el comportamiento de los elementos. Ya hemos visto varios atributos específicos (href, src, type, etc.), pero aquí resumiremos algunos **atributos globales y comunes** que se pueden aplicar a *casi cualquier* elemento HTML:

- **`id`** – Identificador único de un elemento en la página. Sirve para identificar ese elemento de forma *única* dentro del documento (no debe haber dos elementos con el mismo id). Es útil para enlazar (como vimos con anchors `href="#seccion"` apuntando a `id="seccion"`), para aplicar estilos CSS específicos (`#id { ... }`), o para seleccionar ese elemento desde JavaScript. Ejemplo: `<section id="introduccion">...</section>`.

- **`class`** – Nombre(s) de clase(s) que se le asignan a un elemento. A diferencia de id, **puedes usar la misma clase en múltiples elementos**. Las clases sirven principalmente para aplicar estilos con CSS en lote (por ejemplo, `.destacado { color: red; }` aplicaría a cualquier elemento con `class="destacado"`), o para manejar grupos de elementos con JavaScript. Se puede asignar múltiples clases separadas por espacios: `class="btn grande rojo"` (esto asigna tres clases: "btn", "grande" y "rojo" a un mismo elemento).

- **`style`** – Permite agregar **estilos CSS en línea** directamente al elemento. Por ejemplo `style="color: blue; background-color: yellow;"`. Es un atributo poderoso pero, en general, para mantener separada la presentación de la estructura, es mejor usar clases/CSS externo en lugar de style en línea para todo. Sin embargo, es útil para pruebas rápidas o estilos muy específicos.

- **`title`** – Texto de **título informativo**. Al pasar el mouse sobre un elemento con `title`, aparece un cuadrito (tooltip) con ese texto. Se puede usar en casi cualquier elemento para aportar info extra. Por ejemplo: `<p title="Información adicional">Texto del párrafo</p>` (no visible a simple vista, pero con hover sale el tooltip).

- **`alt`** – Ya mencionado en `<img>`, es el texto alternativo. **Solo aplica a ciertas etiquetas, principalmente `<img>`** (también en `<area>` de mapas de imagen, `<input type="image">`, etc.). Es obligatorio en `<img>` para accesibilidad.

- **Atributos de datos personalizados (`data-...`)** – HTML5 permite agregar atributos arbitrarios que comiencen con `data-` para almacenar datos personalizados en elementos, útiles para scripts. Ejemplo: `<div id="producto1" data-id="1234" data-category="books">...</div>`. Estos no afectan la presentación, pero son guardados en el DOM para referencia de JS.

- **`hidden`** – Atributo booleano global; si presente, indica que el elemento está oculto (no se muestra). Es distinto a un estilo CSS display:none (pero efectivamente la representación es la misma). Se usa para marcar elementos que no deberían mostrarse.

- **`lang`** – Define el idioma del contenido de un elemento (ya lo vimos en `<html lang="es">`, pero también podría ponerse en un párrafo específico `lang="en"` si ese párrafo está en otro idioma).

- **`tabindex`** – Controla el orden de tabulación para focus con teclado.

- **`contenteditable`** – Permite que el contenido de un elemento sea editable en el navegador (poco común en páginas estáticas, más en apps web).

Dado que los más comunes son **id, class, style, alt, title**, enfoquémonos en su uso práctico:

**Ejemplo demostrando id, class, style, title:**

```html
<h2 id="seccion1" class="titulo-seccion" title="Título de sección">Sección 1: Introducción</h2>
<p class="texto">Este es un párrafo con clase "texto".</p>
<p class="texto destacado" title="Este párrafo está resaltado">
  Este es un párrafo <span style="color: red; font-weight: bold;">resaltado en rojo</span> 
  que comparte la clase "texto" y además tiene la clase "destacado".
</p>
<img src="imagen.jpg" alt="Descripción de la imagen" title="Imagen de ejemplo" class="marco-sombra">
```

Analicemos:
- El `<h2>` tiene un `id="seccion1"` (podríamos enlazar con `#seccion1` desde un índice, por ejemplo) y también una clase `titulo-seccion` (quizá definida en CSS para dar estilo uniforme a todos los títulos de sección). Además tiene un `title` que al pasar el mouse mostrará "Título de sección".
- Los `<p>` llevan `class="texto"` para quizás aplicarles un estilo común. El segundo `<p>` tiene **dos clases**: "texto" y "destacado". Eso podría significar en CSS que "destacado" añade, por ejemplo, un fondo amarillo. También tiene un `title` que dice "Este párrafo está resaltado".
- Dentro de ese párrafo, el `<span>` utiliza `style="color: red; font-weight: bold;"` para aplicar color rojo y negrita solo a esa porción del texto (inline style, normalmente lo evitaríamos en producción, pero para mostrar el ejemplo está bien).
- La `<img>` tiene `alt`, `title` y también una clase `marco-sombra` (quizá en CSS define un borde y sombra a las imágenes con esa clase, por ejemplo).

En general, **`id` y `class` son fundamentales** para trabajar con CSS y JS. Por ahora, como estamos en HTML puro, no vemos efecto de class e id sin CSS, pero pronto en la siguiente sección veremos cómo usar CSS para estilarlos.

**Ejercicio práctico:** Recorre el código HTML de la página que hayas creado hasta ahora y agrega:
- Un `id` único a cada sección principal (por ejemplo, id="header", id="main", id="footer", id="form-contacto", etc.). Luego, crea en la parte superior de la página una especie de índice con enlaces rápidos usando esos ids (ej: `<a href="#form-contacto">Ir al formulario de contacto</a>`).
- Agrega clases a elementos que tengan un rol similar. Por ejemplo, asigna `class="enlace-externo"` a todos los `<a>` que van fuera de tu sitio, o `class="destacado"` a los párrafos o secciones que quieras resaltar más tarde.
- Pon un par de atributos `title` en distintos elementos: quizá en una imagen (describiendo un poco más), en un enlace (el title de un enlace suele indicar a dónde lleva, por ejemplo `title="Sitio oficial de Python"` en un enlace a python.org).
- (Opcional) Usa un atributo `style` en alguna etiqueta para cambiar algo de apariencia, por ejemplo `style="background-color: lightgray;"` en un `<div>` o sección para darle un fondo gris claro. Solo para probar, luego lo manejaremos con CSS.
- Refresca la página en el navegador y pasa el mouse sobre los elementos con title para ver los tooltips. Verifica que los enlaces con href="#..." funcionan navegando dentro de la página. Las clases e ids por sí solos no cambian nada visualmente sin CSS, pero estás preparando el terreno para estilizar.

## 3. Listado de Etiquetas HTML Útiles y su Descripción

A continuación, se presenta un **resumen de las etiquetas HTML mencionadas** (y otras comunes) junto con una breve descripción de su función. Esto sirve como referencia rápida:

- **`<!DOCTYPE html>`**: Declaración del tipo de documento, debe ir al inicio de todo documento HTML5.

- **`<html>`**: Elemento raíz que envuelve todo el contenido HTML. Atributo común: `lang` para indicar el idioma.

- **`<head>`**: Contenedor de metadatos de la página (no contenido visible). Aquí van `<title>`, `<meta>`, `<link>`, `<style>`, `<script>` y otras metas.

- **`<title>`**: Título de la página mostrado en la pestaña del navegador o en resultados de búsqueda. Debe ir dentro de `<head>` y es obligatorio que exista.

- **`<meta>`**: Metaetiquetas que proveen información. Ejemplos:
  - `<meta charset="UTF-8">` especifica la codificación de caracteres.
  - `<meta name="description" content="Descripción de la página...">` da una descripción (SEO).
  - `<meta name="viewport" content="width=device-width, initial-scale=1.0">` para diseño responsivo en móviles.

- **`<link>`**: Enlace a recursos externos. Se usa sobre todo para **CSS externo**: `<link rel="stylesheet" href="estilos.css">`. Otros usos: iconos (`rel="icon"`), fuentes, etc. Va en `<head>`.

- **`<style>`**: Etiqueta para incluir **CSS interno**. Contiene código CSS entre la apertura y cierre. Ejemplo: `<style> body { background: #eee; } </style>` en el head.

- **`<body>`**: Sección de contenido **visible** de la página. Todo lo que se mostrará al usuario debe estar dentro de `<body>` (aunque `<script>` también puede ir al final del body para cargar JS).

- **`<header>`**: Sección de **encabezado** de la página o sección. Contiene títulos, logos, menús introductorios, etc.

- **`<nav>`**: Sección de **navegación** con enlaces. Usado para menús principales, menús de pie de página, etc.

- **`<main>`**: Indica el **contenido principal** del documento. Debe haber solo uno por página. Contiene el contenido central (artículos, secciones principales, etc.).

- **`<section>`**: Define una **sección genérica** de contenido, agrupando contenido relacionado bajo un tema común. Suele tener un encabezado propio.

- **`<article>`**: Representa un **contenido autónomo** e independiente (artículo, entrada de blog, comentario, post). Puede ser distribuido o reutilizado fuera de contexto y seguir teniendo sentido.

- **`<aside>`**: Contenido **complementario o tangencial** al principal. Ejemplo típico: barras laterales, recuadros de información extra, listas de enlaces relacionados.

- **`<footer>`**: Pie de página o pie de sección. Incluye información de cierre: autor, copyright, enlaces adicionales, navegación secundaria, etc.

- **`<h1> ... <h6>`**: **Encabezados** de nivel 1 a 6. `<h1>` el más importante; `<h6>` el menos. Dan estructura jerárquica al contenido.

- **`<p>`**: **Párrafo** de texto. Contenedor básico para bloques de texto corrido.

- **`<span>`**: **Contenedor en línea genérico**. No tiene significado propio ni estilo por defecto, se usa para agrupar texto o elementos dentro de una línea para propósitos de estilo o scripting.

- **`<strong>`**: Marca **énfasis fuerte** o importancia en el texto. Por defecto se ve en **negrita**.

- **`<em>`**: Marca **énfasis** (énfasis leve o italicización). Por defecto se ve en *cursiva*.

- **`<b>`**: Texto en **negrita** pero sin significado especial (estilístico puro). Semánticamente se usa para texto que se quiere destacar pero que no es más importante (por ejemplo palabras clave). (Uso semántico de `<strong>` es preferible para importancia).

- **`<i>`**: Texto en **cursiva**, sin significado especial (por ejemplo para términos en otro idioma, títulos de obras, o para diferenciación visual). Para énfasis real se prefiere `<em>`.

- **`<br>`**: Salto de línea (break). Inserta una nueva línea donde se coloca.

- **`<hr>`**: Separador temático horizontal (horizontal rule). Representado como una línea horizontal divisoria.

- **`<ul>`**: **Lista no ordenada** (unordered list). Contiene elementos `<li>` y típicamente se muestra con viñetas.

- **`<ol>`**: **Lista ordenada** (ordered list). Contiene `<li>` y se muestra con numeración o letras.

- **`<li>`**: **Elemento de lista** (list item). Debe estar dentro de `<ul>` o `<ol>`. Representa un ítem de la lista.

- **`<dl>`**: **Lista de definiciones**. Contiene `<dt>` (término) y `<dd>` (definición) pares para glosarios o descripciones.

- **`<dt>`**: **Término a definir** en una lista de definiciones.

- **`<dd>`**: **Descripción** o definición de un término previo `<dt>`.

- **`<a>`**: **Enlace (anchor)**. Usado para hipervínculos. Atributo principal: `href` con la URL o destino. Otros: `target` (p.ej `_blank` para nueva pestaña), `title` (info emergente).

- **`<img>`**: **Imagen** embebida. Atributos: `src` (ruta de la imagen, obligatorio), `alt` (texto alternativo, obligatorio), `title` (opcional), `width`, `height` (opcionales para tamaño).

- **`<figure>`**: Contenedor semántico para agrupar contenido ilustrativo (imágenes, diagramas, código, etc.) con su **figura** y subtítulo asociado (ver `<figcaption>`). Por ejemplo, una imagen con pie de foto se envuelve en `<figure>`.

- **`<figcaption>`**: **Pie de figura** o leyenda. Proporciona una leyenda o descripción para el contenido del `<figure>` al que pertenece.

- **`<audio>`**: Inserta contenido **audio** con un reproductor. Atributos clave: `src`, `controls`. Puede contener `<source>` para múltiples formatos y `<track>` para subtítulos/transcripciones.

- **`<video>`**: Inserta un **video** con reproductor. Atributos: `src`, `controls`, `width`, `height`, `poster`, etc. Puede contener `<source>` (múltiples formatos) y `<track>` (subtítulos).

- **`<source>`**: Especifica una **fuente alternativa** para medios `<audio>` o `<video>`. Atributos: `src` (ruta del archivo), `type` (formato MIME). Se usan varios en cascada dentro del elemento padre.

- **`<track>`**: Para **subtítulos** o pistas de texto en audio/video. Atributos: `kind` (ej. "subtitles"), `srclang` (idioma), `label`, `src` (archivo .vtt por ejemplo).

- **`<table>`**: Tabla de datos. Contiene filas `<tr>` y opcionalmente `<thead>`, `<tbody>`, `<tfoot>`.

- **`<tr>`**: Table row, **fila de tabla**. Va dentro de `<table>` (o sus secciones). Agrupa celdas en una fila horizontal.

- **`<th>`**: Table header cell, **celda de encabezado** (normalmente primera fila o primera columna). Por defecto en negrita y centrada. Atributo `scope` opcional para accesibilidad (col, row, etc., indicando si es encabezado de columna o fila).

- **`<td>`**: Table data cell, **celda de datos** normal. Contiene el contenido de esa celda.

- **`<caption>`**: Título o leyenda de la tabla. Suele mostrarse centrado arriba (o abajo) de la tabla. Debe ser el primer hijo de `<table>` si se usa.

- **`<form>`**: Formulario interactivo. Contenedor de campos de entrada. Atributos: `action` (destino al enviar), `method` (GET/POST).

- **`<input>`**: Campo de **entrada genérico**. Atributo *obligatorio*: `type` (text, password, radio, checkbox, submit, etc., según el tipo de control). Otros atributos según tipo: `name`, `value`, `placeholder`, `checked`, `required`, `min`, `max`, etc.

- **`<label>`**: Etiqueta de texto para un control de formulario. Asociada mediante `for` al `id` del input correspondiente. Hace clickeable el texto para enfocar/activar el control.

- **`<textarea>`**: **Área de texto multilínea**. Atributos: `name`, `rows`, `cols`, `placeholder`, etc. Incluye contenido entre apertura y cierre si se quiere texto por defecto.

- **`<select>`**: **Lista desplegable** (combo box). Contiene `<option>` como opciones seleccionables. Puede usar atributo `multiple` para permitir selección múltiple (cambia a lista con ctrl+click por ejemplo en desktop).

- **`<option>`**: **Opción** dentro de un `<select>`. Atributos: `value` (valor enviado del option; si se omite, se envía el texto del option), `selected` (para marcar opción por defecto seleccionada), `disabled` (deshabilitar esa opción).

- **`<button>`**: **Botón** clickeable. Puede contener texto u otros elementos (iconos). Atributo `type`: `"button"` (no acción predeterminada), `"submit"` (envía formulario), `"reset"` (resetea formulario).

- **`<div>`**: Contenedor de **bloque genérico** (division). Es el equivalente en bloque de `<span>`. No tiene significado propio, pero es muy usado para agrupar otros elementos para aplicar estilos o scripts. Antes de HTML5, muchos usábamos `<div>` para todo el layout; con etiquetas semánticas ese uso se reduce, pero `<div>` sigue siendo útil para agrupaciones sin un significado específico. Ej: `<div class="contenedor"> ... </div>`.

- **`<script>`**: Inserta o enlaza **scripts (JavaScript)**. Puede llevar `src="archivo.js"` para incluir un archivo externo, o contener código JS directamente. Por seguridad, en HTML5 también se suele usar atributos como `defer` o `async` para controlar la carga. Normalmente se coloca al final del `<body>` o en `<head>` con defer.

- **`<!-- ... -->`**: **Comentario** en HTML. No es una etiqueta per se de contenido, sino sintaxis para comentar código HTML que no será mostrado en la página ni procesado por el navegador. Útil para dejar notas en el código o para remover temporalmente partes de código. Ejemplo: `<!-- Este es un comentario -->`.

*(Nota: Hay muchas más etiquetas HTML (unas cien aprox.), pero las listadas arriba son las más utilizadas en nivel básico/intermedio. Para una lista exhaustiva, se puede consultar la documentación de MDN o un *cheat sheet* de HTML.)*

## 4. Ejercicios Prácticos Integrados

A lo largo de las secciones anteriores, hemos incluido ejercicios prácticos para que puedas aplicar inmediatamente cada concepto. **La mejor manera de aprender HTML es "haciendo" HTML.** Si aún no lo has hecho, vuelve y realiza cada ejercicio propuesto: crea tus propios archivos HTML, escribe el código de ejemplo, modifícalo, rompe cosas y arréglalas. 

Estos ejercicios incluyen crear estructuras básicas, usar etiquetas semánticas, dar formato al texto, insertar multimedia, armar enlaces, construir listas, tablas y formularios. Al completar cada uno, habrás construido pedazos de páginas web funcionales. Si ya realizaste todos, ¡felicitaciones! Seguramente notas que todos esos fragmentos pueden unirse para construir algo más grande. En la siguiente sección, daremos un paso más incluyendo **CSS básico** para mejorar el estilo, y luego propondremos un **mini proyecto integrador** que combine todo lo visto.

*(Si por alguna razón no realizaste los ejercicios antes, ¡no es tarde! Puedes practicarlos ahora antes de continuar con CSS.)*

## 5. Introducción básica a CSS: Estilos en la página

HTML define la estructura y contenido, pero para darle estilo visual (colores, fuentes, distribución, márgenes, etc.) utilizamos **CSS** (Cascading Style Sheets, u Hojas de Estilo en Cascada). CSS es un lenguaje aparte que trabaja junto con HTML: mientras HTML dice "esto es un párrafo, esto es un encabezado", CSS dice "los párrafos serán de color azul, los encabezados tendrán 24px de tamaño".

Un principio fundamental es la **separación de contenido y presentación**:
- El HTML se encarga del contenido y la semántica (qué es cada bloque de información).
- El CSS se encarga de cómo se ve ese contenido (presentación visual).

### ¿Cómo incluir CSS?

Hay tres formas principales:
1. **CSS Externo:** crear un archivo `.css` separado (por ejemplo `estilos.css`) y enlazarlo con `<link>` en el `<head>` de tu HTML: `<link rel="stylesheet" href="estilos.css">`. Es la manera más organizada, especialmente para proyectos grandes, ya que separa completamente contenido (HTML) de estilos (CSS).
2. **CSS Interno (en el documento):** usar una etiqueta `<style>` dentro del `<head>` de tu HTML y escribir ahí mismo el código CSS. Útil para pruebas rápidas o páginas pequeñas autocontenidas. Ejemplo:
   ```html
   <head>
     ...
     <style>
       /* CSS interno */
       body { background-color: #f0f0f0; }
       h1 { color: navy; }
     </style>
   </head>
   ```
3. **Estilos en línea:** utilizar el atributo `style` en elementos HTML individuales, como vimos anteriormente (`<p style="color: red;">`). Esto aplica un estilo específico directamente a ese elemento. Sin embargo, se recomienda **no abusar** de estilos en línea porque mezclan presentación con contenido y dificultan mantener estilos consistentes.

Para comenzar, podemos usar CSS interno o en línea mientras aprendemos, pero lo ideal es migrar a CSS externo en proyectos reales.

### Sintaxis básica de CSS

CSS se basa en reglas con la sintaxis:
```css
selector {
    propiedad1: valor1;
    propiedad2: valor2;
    ...
}
```
Por ejemplo:
```css
p {
  color: blue;
  font-size: 14px;
}
```
Esto haría que todas las etiquetas `<p>` tengan texto azul y tamaño de fuente 14px.

**Selectores** comunes:
- Selector por **etiqueta**: simplemente el nombre, afecta a todas esas etiquetas (como `p { ... }` a todos párrafos).
- Selector por **clase**: comienza con un punto `.clase`. Afecta a cualquier elemento con `class="clase"`. Ej: `.destacado { background: yellow; }` afectará a `<p class="destacado">` pero no a otros sin esa clase.
- Selector por **id**: comienza con `#` seguido del id. Ej: `#menu { ... }` afectará al elemento con `id="menu"`.
- Selectores **anidados**: puedes especificar jerarquía. Ej: `header h1 { ... }` afectaría solo a `<h1>` que estén dentro de `<header>`.
- Selectores avanzados (pseudo-clases, atributos, etc.) existen, pero por ahora nos centramos en los básicos.

Las **propiedades CSS** son muy numerosas. Veamos algunas esenciales solicitadas:

- `color`: color del texto (acepta nombres de color en inglés, o valores hexadecimales como `#FF0000`, o formato `rgb()`/`rgba()`).
- `background-color`: color de fondo de un elemento.
- `font-size`: tamaño de fuente (ej. `16px`, `1.5em`, etc.).
- `font-family`: tipografía (fuente) a usar (ej. `font-family: Arial, sans-serif;`).
- `font-weight`: grosor de texto (ej. `bold` para negrita).
- `text-align`: alineación de texto (left, right, center, justify).
- `margin`: margen externo de un elemento (espacio fuera de su borde, separándolo de otros elementos). Puede darse en px, em, % etc.
- `padding`: relleno interno de un elemento (espacio entre su contenido y su borde).
- `border`: borde. Se define con estilo, grosor y color, ej: `border: 1px solid black;`.
- `width`, `height`: dimensiones de ancho/alto.
- `display`: tipo de renderizado (block, inline, inline-block, none para ocultar, etc.).
- `background-image`: imagen de fondo (y relacionados: background-repeat, position, etc.).
- etc.

**Ejemplo práctico de CSS interno:**

Supongamos que queremos estilizar nuestra página básica:
- Fondo de la página gris claro.
- Encabezado azul oscuro con texto blanco.
- Enlaces en el nav sin viñetas y horizontales.
- Títulos en un font atractivo y color específico.
- Párrafos con un ancho máximo para comodidad de lectura.
- Clases para destacar elementos importantes con color de fondo amarillo.

En el `<head>` añadiríamos:

```html
<style>
  /* Estilos globales */
  body {
    background-color: #f9f9f9;
    color: #333;
    font-family: Arial, sans-serif;
  }
  h1, h2, h3 {
    color: darkblue;
  }
  h1 {
    text-align: center;
  }
  
  /* Encabezado y navegación */
  header {
    background-color: navy;
    color: white;
    padding: 20px;
    text-align: center;
  }
  nav ul {
    list-style: none; /* quita viñetas */
    padding: 0;
    text-align: center;
  }
  nav ul li {
    display: inline; /* pone los li en línea */
    margin: 0 10px;
  }
  nav a {
    color: white;
    text-decoration: none; /* quita subrayado */
    font-weight: bold;
  }
  
  /* Contenido principal */
  main {
    max-width: 800px;
    margin: 20px auto; /* centra el main horizontalmente con auto left-right */
    padding: 10px;
  }
  p {
    line-height: 1.6; /* espaciado de línea para mejor lectura */
  }
  
  /* Clases utilitarias */
  .destacado {
    background-color: yellow;
    font-weight: bold;
  }
</style>
```

Este CSS es un poco extenso, pero ilustra muchas cosas:
- `body` establece fuente y colores globales.
- `h1, h2, h3` comparten una regla (todos en color darkblue).
- `header` tiene fondo navy y texto blanco, con padding y centrado.
- En `nav ul` quitamos la viñeta con `list-style: none` y centramos. En `nav ul li` usamos `display: inline` para que los `<li>` se comporten como elementos en línea (uno al lado del otro), y les damos margen para separarlos horizontalmente.
- `nav a` estiliza los enlaces de navegación (color blanco en vez de azul/púrpura, sin subrayado, negrita).
- `main` limitamos el ancho a 800px para no tener líneas muy largas, y centramos ese bloque con `margin: auto` en los lados. También margen vertical y padding interno.
- `p` line-height aumenta la separación entre líneas para legibilidad.
- `.destacado` clase con fondo amarillo y texto en bold para destacar.

**Aplicando clases en HTML:**

Si en nuestro HTML marcamos algo con `<p class="destacado">Texto importante</p>`, recibirá ese estilo de fondo amarillo. Si nuestro header nav está estructurado como en ejemplos previos, esos selectores los afectarán.

**Nota:** El tema de *especificidad* y *cascada* en CSS significa que si dos reglas se aplican al mismo elemento, la más específica o la definida más abajo suele ganar. Por ejemplo, si tuvieramos `p { color: black; }` al inicio del CSS, pero luego `.destacado { color: red; }`, un `<p class="destacado">` sería rojo porque la regla de la clase (más específica) prevalece sobre la genérica de `p`.

**Ejercicio práctico (CSS):** 
1. Toma alguna de las páginas HTML que has creado en los ejercicios anteriores (por ejemplo la que hiciste más completa con header, nav, main, etc.). Añade un bloque `<style>` en el `<head>` y escribe reglas CSS para:
   - Cambiar el color de fondo de la página (`body`) y el color por defecto del texto.
   - Estilizar el `<header>`: color de fondo y color de texto contrastante.
   - Quitar el subrayado de los enlaces (`a { text-decoration: none; }`) y quizás cambiar su color.
   - Poner algún color de fondo o estilo distintivo al `<footer>` si tienes uno.
   - Dar estilos a alguna clase que hayas puesto. Si no la pusiste antes, añade `class="destacado"` a un par de elementos en HTML y luego en CSS define `.destacado { background: #ff0; }` (fondo amarillo) o algo para verificar el efecto.
   - Jugar con alguna propiedad de margen/padding: por ejemplo añadir `margin-top: 20px;` a `h1` o `p { margin: 10px 0; }` para espaciar párrafos, etc.
2. Guarda y recarga la página. Ajusta si algo no se ve como querías. Experimenta cambiando valores (colores, tamaños) para ver el impacto inmediato.

Ahora tu página no solo tendrá la estructura correcta, ¡también se verá mucho mejor con los estilos aplicados! Recuerda que CSS es vasto; hemos rascado la superficie. Pero con estas bases puedes cambiar colores, tipografías, distribuciones básicas y resaltar contenido con bastante flexibilidad.

## 6. Mini Proyecto Integrador: Construyendo una Página Web Completa

Ha llegado el momento de poner todo en conjunto. El **mini proyecto integrador** consiste en crear una página web sencilla, pero **completa**, utilizando los conceptos de HTML y CSS vistos:

### Planteamiento del proyecto:

**Crea una página web personal "Mi Página"**, que contenga:
- **Estructura semántica completa:** usar `<header>`, `<nav>`, `<main>`, `<aside>` (opcional) y `<footer>` adecuadamente.
- **Encabezado** (`<header>`): Con el título de la página (por ej. tu nombre o el nombre del sitio) y quizá un eslogan o logo (puede ser una imagen pequeña o simplemente un texto estilizado).
- **Menú de Navegación** (`<nav>`): Una lista de enlaces (`<ul> <li> <a>`) a secciones de la misma página (usando anchors `#`), o si lo prefieres, a otras páginas (puedes crear más de una página para tu "sitio personal": ej. index.html, contacto.html, etc. Si decides hacerlo de una sola página, los enlaces pueden scroll dentro de la página).
- **Contenido principal** (`<main>`): Incluye varias secciones con distinta información. Por ejemplo:
  - `<section>` de "Sobre mí" con un `<h2>` y un par de `<p>` contando quién eres (o de qué trata la página si es temática).
  - `<section>` de "Galería" donde muestres una o dos imágenes (`<img>`) relacionadas con el tema.
  - `<section>` de "Listado de X" (algo que te guste): podría ser una lista `<ul>` de tus hobbies, o una lista `<ol>` de tus logros, etc.
  - `<article>` (si aplica) con algún texto independiente, por ejemplo un pequeño blog post o noticia de ejemplo.
  - Una **tabla** (`<table>`) de información: por ejemplo, si es personal, una tabla con tu horario diario, o con habilidades y nivel (columna habilidad, columna nivel), o si la página es de un proyecto, alguna tabla de datos relevantes.
  - Un elemento multimedia: por ejemplo un `<video>` corto insertado, o un `<audio>` (si no tienes archivos, podrías incrustar un video de YouTube usando `<iframe>` embebido, pero eso no lo cubrimos explícitamente; opcional).
- **Barra lateral** (`<aside>`): Opcional, solo si tiene sentido para tu contenido. Podría contener un breve listado de enlaces relacionados, un recuadro con citas o datos curiosos, o quizá un pequeño anuncio ficticio. Ubícala dentro de `<main>` o fuera, según cómo quieras el diseño (comúnmente se coloca dentro de main como contenido relacionado).
- **Formulario de Contacto** (`<form>`): Incluye un formulario para que los usuarios te envíen un mensaje:
  - Campos típicos: nombre, email, mensaje (textarea).
  - Quizá opciones como motivo de contacto (select con opciones: Sugerencia, Consulta, Saludo).
  - Botón de enviar.
  - (No es necesario que funcione el envío real, solo la estructura del formulario).
- **Pie de página** (`<footer>`): Con información de pie como copyright (ej. "© 2025 Tu Nombre"), enlaces a redes sociales (pueden ser simples textos o iconos si te animas, o enlaces ficticios), y/o un pequeño texto de despedida.

**Estilos CSS:** Aplica un archivo CSS o un bloque `<style>` para embellecer tu página:
- Define colores de fondo para encabezado y pie (suelen ser llamativos u oscuros) y color de texto que contraste.
- Aplica alguna fuente diferente para los títulos vs. el cuerpo de texto (puedes usar fuentes estándar del sistema o enlazar Google Fonts si te aventuras).
- Estiliza el menú de navegación (`<nav>`): por ejemplo, horizontal en un header, con fondo distinto al resto. Al pasar el mouse sobre los enlaces (`a:hover` en CSS) cambia su color para un efecto interactivo.
- Coloca el main y aside de forma adecuada: puedes usar CSS para que el `<aside>` aparezca alineado a la derecha del contenido principal, por ejemplo, usando `float: right; width: 30%;` en aside y `width: 65%; float: left;` en main, o usando métodos modernos como flexbox o grid (tema avanzado, opcional). Si no quieres complicarte, está bien que aside simplemente esté después de main o antes, en bloque normal.
- Da estilos a la tabla: por ejemplo, un borde colapsado (`border-collapse: collapse;` en table), estilos de fondo alternados a las filas (`nth-child` pseudo-clase, opcional), o al menos bordes a las celdas.
- Estiliza el formulario: hacer que los labels se muestren en bloque encima de los campos (p.ej. `label { display: block; margin-top: 10px; }`), estilizar el botón (colores de fondo, borde, cursor pointer al hover).
- Usa clases para destacar cosas: por ejemplo, si tienes elementos a los que quieres resaltar (como un texto importante), reutiliza la clase `.destacado` con un fondo o borde especial.

No temas a ser creativo: puedes agregar imágenes decorativas, usar colores que te gusten, etc. El objetivo es aplicar *todo lo aprendido*: estructura HTML correcta, variedad de elementos (texto, imagen, lista, tabla, formulario, enlace...), atributos adecuados (alt en imágenes, href en enlaces, etc.), y luego los estilos CSS para lograr una presentación agradable.

### Consejos:
- **Planifica la estructura**: Antes de codear, escribe en papel o en un esquema qué secciones tendrá tu página y qué irá en cada una. Así podrás ir creando el HTML ordenadamente.
- **Construye paso a paso**: Primero arma todo el HTML con la estructura y contenido. Verifica en el navegador que todo el contenido aparece (sin estilos se verá feo, pero al menos sabes que está ahí). Corrige cualquier error de anidación o etiqueta mal escrita.
- **Luego pasa a CSS**: Empieza dando estilos generales (body, fuentes, etc.), luego ve secciones (header, nav, main, footer), y después detalles (clases, etc.). Refresca con frecuencia para ver cambios.
- **Prueba en diferentes tamaños** de ventana, aunque con lo básico está bien. Si quieres, experimenta haciendo la página responsiva (por ejemplo, que el aside se ponga debajo de main en pantallas pequeñas usando @media queries), pero eso es contenido de CSS avanzado/no obligatorio.
- **Valida tu HTML/CSS**: Puedes usar validadores en línea (como el validador W3C) copiando tu código, para ver si hay errores de sintaxis.

Este mini proyecto consolidará tus conocimientos de HTML de nivel básico-intermedio y te dará un resultado tangible: una página web estática construida por ti. ¡Mucha suerte y diviértete en el proceso de creación! 

Una vez terminado, ábrelo en tu navegador, revisa que todos los enlaces funcionan, que las imágenes cargan, que el formulario se ve bien, etc. Incluso puedes mostrárselo a un amigo o familiar abriendo el archivo HTML en su computador o enviándoselo. Acabas de crear una página web desde cero con tus propias manos, usando HTML y CSS 😀. ¡Felicidades!

