# Introducción a HTML y CSS - M03

## Resumen

HTML describe el contenido de una página mediante elementos (pares de etiquetas) que pueden anidarse y modificarse con atributos. CSS define la presentación mediante estilos, que pueden ir en línea, en una hoja de estilo interna o en una externa, y se aplican con selectores de elemento, id o clase. El modelo de cuadro CSS trata cada elemento como un cuadro con contenido, relleno, borde y márgenes. El documento cierra con buenas prácticas: doctype correcto, hojas de estilo, etiquetas de cierre, guardado y revisión frecuentes, y uso de un IDE.

## Conceptos clave

- **Elemento y etiqueta:** un elemento es un par de etiquetas (apertura y cierre) que envuelve contenido.
- **Lenguaje declarativo:** HTML dice qué debe mostrarse, no cómo lo implementa el explorador.
- **Analizador (parser):** herramienta que interpreta el marcado; el explorador web es un ejemplo.
- **Anidamiento, padre e hijo:** un elemento dentro de otro es hijo; el que lo contiene es padre.
- **Herencia y sustitución:** el hijo toma estilos del padre o los reemplaza con un valor propio.
- **Atributo:** característica en la etiqueta de apertura que modifica el elemento (`style`, `id`, `class`, `href`, `src`...).
- **Elementos semánticos:** nombres que describen su contenido (`section`, `article`, `time`, `nav`, `ul`, `ol`, `li`...).
- **CSS (hojas de estilo en cascada):** lenguaje para describir estilo, diseño y presentación.
- **Selector:** parte del estilo que indica a qué elementos se aplica (id, clase, elemento).
- **Modelo de cuadro CSS:** cada elemento ocupa un cuadro con contenido, relleno, borde y márgenes.
- **Separación de intereses:** el contenido va en HTML y la presentación en CSS.
- **IDE:** software que agrupa en una sola interfaz las herramientas del desarrollador.

## Detalle por tema

### Módulo 1 - Configurar una página web con HTML

**Vocabulario previo.** El material define términos base: evento (cualquier cambio en la página), factor de forma (tamaño y diseño del dispositivo), IDE, marcado (describir el contenido encapsulándolo en símbolos), metadatos (información sobre el sitio que usan buscadores y automatizaciones, no el usuario), analizador, referencia (indica dónde está un recurso como una imagen o un script), representación (convertir el código en una página visible), sitio reactivo (se adapta a distintos dispositivos y pantallas), script (programa legible que se ejecuta cuando se necesita), autodescriptivo (el nombre indica la finalidad), estándar, ente normativo (organización que define estándares), estilo, hoja de estilo y sintaxis.

**Etiquetas y elementos.** Una etiqueta es un nombre entre corchetes angulares. La de cierre añade una barra inclinada antes del nombre. Ejemplo: el elemento de énfasis usa el nombre `em`.

**Exploradores y estándares.** HTML es declarativo. El organismo WHATWG define las reglas que los analizadores deben soportar. La especificación de `em` solo exige que el texto destaque; muchos exploradores lo muestran en cursiva, pero no es un elemento de cursiva genérico: para cambiar de "voz" se prefiere `i`, y para expresar importancia, `strong`.

**Anidamiento.** Se compara con meter bolsas pequeñas por categoría dentro de una maleta. El anidamiento da estructura al documento y permite que los hijos hereden propiedades de estilo del padre (por ejemplo, un padre en negrita).

**Anatomía de una página.** Todo documento incluye:

- Declaración `<!DOCTYPE html>`: indica la versión de HTML.
- `<html>`: envuelve todo lo demás.
- `<head>`: metadatos, scripts, estilos y otros recursos; normalmente no se ve.
- `<body>`: la mayor parte del contenido visible; puede usar los recursos definidos en `head`.

`head` y `body` van anidados dentro de `html`.

**Elementos comunes.**

| Elemento | Uso |
|---|---|
| `<p>` | Texto que fluye junto; suele tener margen arriba y abajo |
| `<h1>` a `<h6>` | Jerarquía de títulos; `h1` es el nivel más alto. No confundir con `<head>` |
| `<a>` | Enlace a otro documento o recurso; requiere información adicional |
| `<span>` | Texto a nivel de palabra u oración, útil para dar estilo a fragmentos |
| `<blockquote>` | Cita de otra fuente |
| `<br>` | Salto de línea; sin etiqueta de cierre |
| `<img>` | Imagen; requiere el atributo `src` con una ubicación válida |
| `<hr>` | Salto visual, normalmente una línea horizontal; sin etiqueta de cierre |

**Aplicación a un CV.** El material propone: `p` para nombre, dirección y teléfono; `img` para la foto; encabezados para las secciones; `hr` para separar datos personales de historial laboral; `blockquote` para el comentario de un empleador anterior.

### Módulo 2 - Controlar elementos con atributos

Un atributo modifica un elemento y se escribe en la etiqueta de apertura, tras el nombre y antes del corchete de cierre. Sirve para cambiar el estilo, fijar propiedades (destino de un enlace), enlazar con funciones de JavaScript mediante atributos de suceso y aportar metadatos (visibilidad en buscadores, accesibilidad para lectores de pantalla).

Un atributo puede tener sus propios valores o propiedades. Por ejemplo, `style` contiene propiedades como `color` o `font-weight`, separadas por punto y coma, y todas afectan al elemento padre.

**Atributos habituales.**

- Estilo y diseño: `style` (propiedades y valores en línea), `id` (referencia a un estilo de id, usado por un solo elemento), `class` (referencia a un estilo de clase, reutilizable), `display` (cómo se presenta el elemento respecto a otros; `inline` coloca elementos contiguos en horizontal), `aria-label` (etiqueta para tecnología de asistencia).
- Acción: `href` (destino de un enlace), `src` (ubicación de un recurso multimedia), `autofocus` (el elemento recibe el foco al cargar), `draggable` (si se puede arrastrar).
- Suceso: `onclick` (clic), `onerror` (error), `onkeypress` (tecla pulsada), `onscroll` (desplazamiento); ejecutan una función de script.

El material insiste en saber leer código ajeno, no solo escribirlo.

### Módulo 3 - Organizar el código

**Por qué organizar.** Para el desarrollador: encontrar código con más facilidad al retomar un proyecto, colaborar mejor y acelerar la carga (por ejemplo, scripts en `head`). Para el usuario: la información se encuentra con más facilidad (elementos similares agrupados, espacio negativo suficiente, menús razonables, tipografías y colores coherentes) y admite búsqueda, porque los buscadores están diseñados para localizar elementos semánticos.

**Técnicas para desarrolladores.**

- **Comentarios:** delimitan secciones, documentan y guardan pendientes. No se ven en la página, pero el código fuente sí es accesible al usuario, así que no se debe poner en ellos nada que deba ser privado. Cada lenguaje tiene su propia sintaxis de comentario.
- **Convenciones de estilo de código:** patrones coherentes de nombres.
  - Bicapitalización (camel case): primera palabra en minúscula y las siguientes con inicial mayúscula; útil para funciones.
  - Notación con puntos: separar palabras con un punto en ciertos objetos; puede combinarse con la bicapitalización.
  - Estilo kebab: minúsculas separadas por guiones; es la norma para nombrar estilos en hojas de estilo.
- **Elementos semánticos:** `section` y `article` dividen la información en bloques lógicos (útil también para buscadores); `time` marca contenido temporal, como horarios; `nav` agrupa elementos de navegación, como una lista de enlaces.
- **Sección de cabecera correcta:** en la página principal (`index.html` o `default.html`) conviene colocar en `head` lo que usará todo el sitio, porque es lo primero que se carga. Si una hoja de estilo se carga en `body`, algunos elementos podrían verse mal. Qué incluir:
  - Metadatos (redes sociales, indexación en buscadores), mediante elementos `meta` con atributo `name`.
  - Scripts, a menudo bibliotecas de código abierto, referenciados con `src`.
  - Fuentes personalizadas, referenciadas en la cabecera para que todos los usuarios puedan verlas.
  - Hojas de estilo, para que los estilos estén disponibles para los elementos que los necesiten.

**Técnicas para usuarios.** La arquitectura de información es el plan de cómo se organiza, se enlaza, se accede y se presenta la información en el sitio. Herramientas HTML:

- **Listas:** mantener los elementos concisos, usarlas para tipos concretos de información (las narrativas van en párrafos), una idea por elemento y revisar que se vean bien en móvil y en pantallas grandes. Tipos: desordenada (`ul`), ordenada (`ol`) y de descripciones (`dl` con `dt` para el término y `dd` para la descripción). `ul` y `ol` usan `li`. El estilo de las viñetas se puede cambiar con CSS.
- **Tablas:** presentan datos de forma estructurada. Antiguamente se usaban para maquetar; desde HTML4 se desaconseja y HTML5 con CSS3 ofrecen alternativas, aunque conviene conocer ese uso por si aparece en sitios existentes.

### Módulo 4 - Codificar con estilo: CSS

**Qué es.** El estilo (colores, fuentes, etc.) puede aplicarse con estilos en línea (atributo `style`, a nivel de elemento) o con una hoja de estilo (colección de estilos). CSS significa "hojas de estilo en cascada" y se usa con lenguajes de marcado como HTML; separa la presentación del contenido. El término "hojas de estilo" no limita CSS a ellas: también cubre el estilo en línea.

**Cascada: herencia y sustitución.**

- Herencia: un hijo recibe los estilos del padre si no define los suyos.
- Si el hijo añade su propio margen izquierdo, el material indica que la sangría resultante suma la del padre y la del hijo (10 px + 20 px = 30 px), mientras que el padre conserva 10 px.
- Sustitución: si una propiedad solo admite un valor (como `color`), el valor del hijo reemplaza al del padre.
- La sangría del código fuente es solo para legibilidad; no afecta a lo que ve el usuario.

**Estilos en línea.** Sirven para sitios sencillos con pocos estilos, pero cuantos más hay, más difícil es gestionarlos; cambiar un estilo repetido obliga a modificar cada elemento.

**Hojas de estilo.**

- Externa: archivo `.css` referenciado desde `head` con el elemento `link` y el atributo `href`. Es la opción recomendada.
- Interna: elemento `style` dentro de `head`. Útil para pruebas o una página temporal única.

**Anatomía de un estilo en hoja de estilo.**

- Selector: indica el tipo de estilo y a qué elementos se aplica.
- Nombre de nodo: nombre del selector, sin espacios; se recomienda estilo kebab.
- Propiedad: parte del elemento que cambia.
- Valor: unidad (como `10px`) o término (como `bold`); a veces ambos son equivalentes, como en `font-weight` con 700 o bold.
- Declaración: combinación de propiedad y valor.
- Bloque de declaración: conjunto de declaraciones entre llaves.

**Tipos de selector y cómo se aplican.**

| Selector | Símbolo | Alcance | Aplicación en HTML |
|---|---|---|---|
| Id | `#` | Un solo elemento | Atributo `id`; si se repite, el explorador estiliza el primero que encuentra |
| Clase | `.` | Cualquier cantidad de elementos | Atributo `class` |
| Elemento | nombre del elemento | Todos los elementos con ese nombre | Automático, sin atributos |

Si el mismo selector aparece varias veces en una hoja, el explorador combina sus estilos.

### Módulo 5 - Modelo de cuadro CSS

**Por qué.** Maquetar con tablas no se considera buena práctica por su falta de flexibilidad. El modelo de cuadro imita filas y columnas con más flexibilidad. Ventajas: diseño reactivo (adaptación a cualquier factor de forma), mayor capacidad de personalización y mejor accesibilidad (con tablas, los lectores de pantalla deben anunciar fila y columna en cada celda).

**Componentes.** Cada fragmento de contenido tiene su cuadro, con cuatro partes (el material usa la analogía de una parcela con casa, jardín, cerca y aceras):

- Área de contenido: donde está el contenido principal, con altura y anchura.
- Relleno: distancia entre el contenido y el borde.
- Borde: línea visible alrededor del cuadro; si no se especifica, no hay borde.
- Márgenes: distancia respecto a otros cuadros.

**Valores.** Los píxeles (`px`) dan una medida fija, igual en cualquier pantalla. Altura y anchura pueden ser estáticas o dinámicas, y admiten máximo y mínimo. Márgenes y relleno se definen arriba, abajo, izquierda y derecha, y pueden ser estáticos o dinámicos. Los bordes pueden tener el mismo tamaño o tamaños distintos por lado.

**Ejemplo del material.** Un cuadro de 1024 px de alto (estático) y 100 % de ancho (dinámico); con márgenes definidos, otro cuadro debajo queda separado por el margen (50 px en el ejemplo) salvo que tenga su propio margen superior; con relleno de 10 px, el contenido siempre queda a 10 px del borde izquierdo.

**Crear un cuadro.** Pasos para la sección principal: crear un selector de id autodescriptivo (se usa id porque solo se aplicará a un cuadro), fijar `width` y `height`, y aplicar el id a un `div`. Margen y relleno se establecen igual.

### Módulo 6 - Buenas prácticas de HTML y CSS

Una buena práctica es un estándar o convención que asegura coherencia, previsibilidad y calidad; puede definirse a nivel de equipo o de sector. Cuatro prácticas:

1. **Doctype correcto.** El explorador necesita saber la versión del lenguaje. Va como primera línea, antes de `head`. En HTML5 es `<!DOCTYPE html>`. Otras versiones (HTML4) usan una declaración distinta y más larga. No es un elemento ni una etiqueta, no lleva cierre y no distingue mayúsculas de minúsculas (aunque se suele escribir `<!DOCTYPE html>`).
2. **Hojas de estilo en lugar de estilos en línea.** Razones: tamaño y velocidad (menos código repetido, menor tiempo de carga), mantenimiento (todo en un lugar; mezclar externos, internos y en línea obliga a revisar tres ubicaciones) y separación de intereses (HTML para contenido y estructura, CSS para presentación).
3. **Cerrar las etiquetas.** Aunque los exploradores toleran omisiones, cerrar ayuda a que la página sea ágil (el explorador analiza carácter a carácter y delimita el ámbito del contenido), compatible con más exploradores (no todos corrigen errores) y legible para el equipo y para diagnosticar fallos.
4. **Guardar y revisar con frecuencia.** Guardar evita pérdidas; probar con frecuencia (cada pocas líneas al empezar, o tras cada componente, como un formulario completo) facilita localizar errores.

**IDE.** Software con interfaz central que simplifica el flujo de trabajo y ayuda a seguir buenas prácticas. Funciones: editor de código, realce de sintaxis (colores y efectos que muestran estructura y errores), finalización de código (autocompletado; puede añadir etiquetas de cierre), autoguardado y depuración integrada. Se puede escribir código también en un editor de texto simple.

## Código y ejemplos

Esqueleto mínimo de un documento HTML con elementos anidados (resultado: una página con un título y un párrafo con una palabra enfatizada).

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Recursos de la página: no se muestran al usuario -->
  </head>
  <body>
    <h1>Mi bitácora de viajes</h1>
    <p>Hoy visité <em>Lisboa</em> por primera vez.</p>
  </body>
</html>
```

Anidamiento y estilo en línea con dos propiedades (resultado: texto azul y en negrita, con el `div` como padre de dos párrafos).

```html
<div style="color: blue; font-weight: bold;">
  <p>Primer aviso</p>
  <p>Segundo aviso</p>
</div>
```

Atributos de acción y de suceso (resultado: un enlace, una imagen y un botón que ejecuta la función `saludar` al hacer clic).

```html
<a href="https://example.com">Ir al ejemplo</a>
<img src="imagenes/gato.jpg">
<button onclick="saludar()">Saludar</button>
<script>
  function saludar() {
    alert("Hola");
  }
</script>
```

Listas ordenada, desordenada y de descripciones (resultado: lista numerada, lista con viñetas y pares término-descripción).

```html
<ol>
  <li>Mezclar</li>
  <li>Hornear</li>
</ol>
<ul>
  <li>Harina</li>
  <li>Azúcar</li>
</ul>
<dl>
  <dt>HTML</dt>
  <dd>Lenguaje de marcado</dd>
  <dt>CSS</dt>
  <dd>Lenguaje de estilos</dd>
</dl>
```

Cabecera de la página principal con metadatos, scripts y hoja de estilo (resultado: los recursos se cargan antes que el cuerpo).

```html
<head>
  <meta name="description" content="Bitácora personal de viajes">
  <script src="js/utilidades.js"></script>
  <link rel="stylesheet" href="css/estilos.css">
</head>
```

Los tres selectores en una hoja de estilo y su aplicación (resultado: todos los `p` con margen izquierdo, un único elemento con id en negrita y los elementos con clase en rojo).

```css
/* selector de elemento: afecta a todos los p */
p { margin-left: 15px; }

/* selector de id: un solo elemento */
#titulo-principal { font-weight: bold; }

/* selector de clase: varios elementos */
.texto-alerta { color: red; }
```

```html
<p id="titulo-principal">Texto en negrita</p>
<p class="texto-alerta">Aviso en rojo</p>
<p class="texto-alerta">Otro aviso en rojo</p>
```

Herencia y sustitución (resultado: el primer párrafo se desplaza 25 px a la izquierda según la suma descrita en el material; el segundo texto se ve en verde porque sustituye el color del padre).

```html
<div style="margin-left: 5px;">
  <p style="margin-left: 20px;">Sangría acumulada</p>
</div>

<div style="color: red;">
  <p style="color: green;">Color sustituido</p>
</div>
```

Hoja de estilo interna (resultado: todos los `p` de esa página con margen izquierdo, sin archivo externo).

```html
<head>
  <style>
    p { margin-left: 30px; }
  </style>
</head>
```

Cuadro CSS para una sección principal (resultado: bloque con 80 % de ancho, 300 px de alto, relleno, borde y separación con elementos vecinos).

```css
#portada-sitio {
  width: 80%;
  height: 300px;
  margin: 40px;
  padding: 12px;
  border: 2px solid gray;
}
```

```html
<div id="portada-sitio">
  Contenido de la portada
</div>
```

## Errores comunes

- Omitir etiquetas de cierre: puede ralentizar el análisis y producir fallos en exploradores que no corrigen el HTML mal escrito.
- Mezclar estilos externos, internos y en línea: obliga a buscar en tres sitios al cambiar el diseño.
- Cargar la hoja de estilo en `body`: algunos elementos pueden mostrarse incorrectamente.
- Repetir un `id` en varios elementos: solo se estiliza el primero que encuentra el explorador.
- Confundir `<head>` con `<h1>`-`<h6>`: el primero es una sección del documento, los segundos son títulos.
- Usar `em` como cursiva genérica o para dar importancia: para eso existen `i` y `strong`.
- Dejar en los comentarios información que no debe ser pública: el código fuente es visible al usuario.
- Usar tablas para maquetar: poco flexible y menos accesible; usar el modelo de cuadro CSS.
- Esperar a terminar para probar el código: dificulta localizar los errores.

## Herramientas

- **Explorador web:** actúa como analizador y representa la página.
- **IDE:** editor de código, realce de sintaxis, finalización de código, autoguardado y depuración integrada.
- **Editor de texto simple:** suficiente para escribir HTML, CSS y JavaScript.
- **Bibliotecas de código abierto:** el material cita jQuery y Bootstrap como ejemplos de scripts referenciados desde `head`.

## Preguntas de repaso

1. ¿Qué significa que HTML sea un lenguaje declarativo?
   **Respuesta:** Que describe las reglas de qué debe mostrar y cómo debe actuar una página, pero no cómo debe implementarlas el explorador.

2. ¿Qué cuatro elementos o declaraciones forman la estructura básica de todo documento HTML y cómo se relacionan?
   **Respuesta:** La declaración `<!DOCTYPE html>` y los elementos `html`, `head` y `body`; `head` y `body` están anidados dentro de `html`.

3. ¿Qué diferencia hay entre un selector de id y uno de clase?
   **Respuesta:** El de id (`#`) se aplica a un solo elemento mediante el atributo `id`; el de clase (`.`) puede aplicarse a cualquier cantidad de elementos mediante el atributo `class`.

4. ¿Cuáles son los componentes del modelo de cuadro CSS y qué controla cada uno?
   **Respuesta:** Área de contenido (con su altura y anchura), relleno (distancia del contenido al borde), borde (línea visible alrededor) y márgenes (distancia a otros cuadros).

5. ¿Por qué se recomienda usar hojas de estilo externas en lugar de estilos en línea?
   **Respuesta:** Reducen el tamaño de los archivos y el tiempo de carga, concentran los estilos en un solo lugar para facilitar el mantenimiento y aplican la separación de intereses entre contenido y presentación.
