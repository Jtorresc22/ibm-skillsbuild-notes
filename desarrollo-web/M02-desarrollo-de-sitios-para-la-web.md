# Desarrollo de sitios para la web - M02

## Resumen
El explorador web interpreta marcado (HTML) para representar contenido; el marcado es texto abierto que enlaza recursos en lugar de incrustarlos. HTML define la estructura, CSS la presentación y JavaScript la interacción. HTML5 trajo etiquetas semánticas y funciones que sustituyeron a complementos como Flash. Para organizar el trabajo se usa el SDLC, con enfoque en cascada o ágil (Scrum).

## Conceptos clave
- **Explorador web:** software para visualizar sitios e intercambiar información con ellos.
- **Marcado:** instrucciones que envuelven el contenido y dicen al explorador cómo mostrarlo.
- **Representación (rendering):** el explorador interpreta el marcado y da formato al contenido.
- **HTML:** lenguaje de marcado de hipertexto para el contenido web.
- **Elemento, etiqueta, atributo:** un elemento = etiqueta de apertura + contenido + etiqueta de cierre; los atributos aportan datos extra.
- **Lenguaje declarativo:** describe qué mostrar, no cómo procesarlo (HTML y CSS).
- **Etiqueta semántica:** su nombre indica con claridad su función (article, footer).
- **CSS:** hojas de estilo en cascada; los hijos heredan el estilo del padre salvo que lo sustituyan.
- **Selector:** de elemento, de clase (`.`) o de id (`#`).
- **Lenguaje de script / JavaScript:** lenguaje interpretado que aporta interactividad.
- **Suceso (event), escucha, manejador:** acción en la página, quien la recibe y el código que responde.
- **SDLC:** planificación, diseño, desarrollo, pruebas, lanzamiento, mantenimiento.
- **Cascada vs. ágil; Scrum:** proceso secuencial frente a entregas incrementales e iterativas.

## Detalle por tema

### Exploradores web y marcado
- Ejemplos de exploradores: Edge, Firefox, Chrome, Safari.
- El marcado envuelve el contenido con instrucciones (por ejemplo, `<b>` para negrita, `<ul>`/`<li>` para listas con viñetas).
- Retos que resuelve el marcado, con el ejemplo de un informe de procesador de textos enviado por correo:
  - **Incrustación:** el documento guarda dentro los archivos (imágenes, diagramas), así que pesa más y cada copia enviada repite todo. El marcado enlaza a los recursos en otra ubicación.
  - **Cantidad:** mover muchos datos exige ancho de banda (cantidad de datos que la red transmite en un periodo), que es limitado. El marcado es texto y consume menos.
  - **Apertura:** un formato ligado a una aplicación de propiedad (código cerrado) solo lo abre quien la tiene. El marcado es abierto: cualquier aplicación que interprete HTML puede representarlo.
- Experiencia en el explorador: antes algunos exploradores ignoraban los estándares; hoy se alinean con ellos. Aun así, el desarrollador debe cuidar tres puntos: cómo se ve el contenido en distintos tamaños de pantalla, cómo cada dispositivo almacena datos y qué prestaciones tiene cada explorador (los móviles pueden carecer de algunas, y no todos implementan toda la especificación HTML). No se puede dar la misma experiencia en todas las plataformas, pero sí buscar las mismas funciones para todos.

### HTML: el lenguaje de la web
- **Historia:**
  - GML: esquema de marcado creado por tres ingenieros de IBM a finales de los 60; tenía etiqueta de apertura (`:h1`) pero no de cierre.
  - SGML: evolución de GML con corchetes angulares y anidamiento; más permisivo que HTML (cierre no obligatorio, otros símbolos posibles).
  - HTML: creado en 1989 por el creador de la World Wide Web, basado en SGML y con etiquetado para enlazar documentos y activos.
- **Estructura de documento:** elemento raíz `html`, sección `head` (scripts, hojas de estilo, metadatos) y sección `body` (contenido visible). Un esquema define qué está permitido; un documento que lo cumple está bien formado. XML tiene estructura parecida pero centrada en objetos de datos.
- **Estructura de etiquetas:** instrucciones entre corchetes angulares; ejemplos de nombres: `strong`, `a` (ancla), `i`.
- **Usos de los atributos:** estilo (`style`), recursos (`href` en `a`), sucesos (`onclick`) y metadatos (`type=button`).
- **Declarativo:** HTML indica qué mostrar, no cómo. El elemento `i` solo declara que el texto contrasta con la prosa normal; que se vea en cursiva es decisión del explorador. El analizador (parser) busca etiquetas y aplica el formato.
- **Evolución:** en HTML5 se difuminan las distinciones entre presentación, sucesos y datos. Se prefiere `em` frente a `i`/`b` por compatibilidad y accesibilidad: indica énfasis y cada explorador o herramienta de accesibilidad lo expresa a su manera.

### HTML5: la evolución del hipertexto
- Antes se dependía de programas externos al explorador para animación e interactividad. Flash cumplía ese papel, pero no funcionaba en móviles, tenía problemas de seguridad y exigía instalar un complemento. HTML5 lo dejó obsoleto.
- La interactividad de HTML5 requiere JavaScript y CSS.
- **Mejoras generales:** más etiquetas semánticas (frente a `div`, genérica, aparecen `article` y `footer`); HTML se centra en estructura y contenido y deja el diseño gráfico a CSS.
- **Datos y conectividad:** HTML5 acerca a la web funciones como el guardado automático. Para un manejo de datos robusto se recurre a marcos (frameworks) de JavaScript, que se apoyan en HTML5.
- **Interactividad:** gráficos y vídeo sin complementos de terceros y API de geolocalización.
- **Aplicaciones web:** accesibles desde el explorador y comparables a las de escritorio.
- **Compatibilidad:** la especificación es amplia y cambia; cada fabricante decide cómo la implementa. Hay sitios para probar páginas en distintas configuraciones y el desarrollador debe mantenerse al día.

### Función de CSS: aplicar estilo
- Los primeros documentos HTML eran solo texto con enlaces. Algunos exploradores incluyeron sus propios lenguajes de estilo, lo que complicaba el trabajo; CSS se propuso en 1994 y se estandarizó. La adopción por exploradores como Netscape Navigator e Internet Explorer lo consolidó.
- CSS es declarativo: define reglas que el explorador debe admitir, sin decir cómo.
- El estilo trata de la experiencia de todos los usuarios, no solo del aspecto visual.
- **Estilo en línea:** atributo `style` dentro de la etiqueta. Se vuelve inmanejable al crecer, porque hay que repetirlo y cambiarlo elemento por elemento. Una hoja de estilo es una colección de estilos que lo evita.
- **Cascada:** un elemento padre envuelve a sus hijos; los hijos heredan el estilo salvo que declaren la misma propiedad con otro valor.
- **Sintaxis:** selector (elemento, `.clase` para muchos elementos, `#id` para uno solo), nombre del estilo sin espacios (se recomienda bicapitalización, como `miNuevoEstilo`) y bloque de declaración entre llaves con propiedades y valores.

### Función de JavaScript: interacción
- HTML y CSS se centran en estructura y presentación; las interacciones (vídeo, arrastrar y soltar, menús desplegables, corrector ortográfico) necesitan un lenguaje de script.
- **Script vs. compilado:**

| Aspecto | Lenguaje de script (interpretado) | Lenguaje compilado |
|---|---|---|
| Legibilidad | Legible por personas al escribir y al ejecutar | Se traduce a código de máquina |
| Cambios | Se edita el archivo y se sube al servidor | Hay que volver a traducir |
| Velocidad | Más lento (se traduce al ejecutar, línea a línea) | Más rápido |

- **Historia:** creado en Netscape para hacer páginas dinámicas; estandarizado por ECMA, cuyo estándar genérico es ECMAScript. Mantiene retrocompatibilidad, por lo que ofrece varias formas de hacer lo mismo.
- **Java no es JavaScript:** Java es compilado y de otra empresa; el nombre fue marketing, sin relación real.
- JavaScript no es estrictamente orientado a objetos; TypeScript (Microsoft) se transpila a JavaScript antes de publicar.
- **Sucesos:** una acción del usuario dispara un suceso; la escucha lo recibe y el manejador (escrito en JavaScript) ejecuta la tarea. El script puede ir en el HTML o en un archivo separado compartido.
- JavaScript también gestiona datos y puede crear HTML y CSS dinámicamente. Con `querySelector` localiza elementos por selector CSS (por ejemplo, por id) para validar campos, como avisar de que un campo obligatorio está vacío al enviar un formulario.

### De los requisitos al lanzamiento (SDLC)
- El ciclo de vida surgió en los años 60 para gestionar proyectos de software grandes; ofrece pasos y entregables estándar.
- **Fases:**
  1. Planificación: recopilar requisitos de las partes interesadas, definir objetivos, público y tipos de contenido.
  2. Diseño: además del aspecto visual, mapa del sitio (modelo jerárquico de páginas), estructura de navegación (cómo se conectan las páginas; suele ser el menú) y arquitectura de la información (organizar y etiquetar contenido para encontrarlo). También planifica multimedia.
  3. Desarrollo: construir con HTML, CSS y JavaScript a partir de requisitos y wireframes.
  4. Pruebas: usabilidad, accesibilidad y cumplimiento de requisitos, con QA.
  5. Lanzamiento: publicar los archivos en el servidor.
  6. Mantenimiento: revisar comentarios, soporte y avances tecnológicos y actualizar contenido y multimedia.
- **Cascada:** fases en secuencia descendente. Desventajas: ciclos largos (el producto puede quedar obsoleto), poca interacción con el usuario y pruebas al final (arreglos costosos).
- **Ágil:** nace a comienzos de los 2000 con un manifiesto de cuatro valores: personas e interacciones sobre procesos y herramientas; software en funcionamiento sobre documentación extensiva; colaboración con el cliente sobre negociación contractual; responder al cambio antes que seguir un plan. Entrega en pequeños incrementos.
- **Scrum:** enfoque iterativo del enfoque ágil. Equipos pequeños trabajan en sprints (plazo definido con una porción pequeña de trabajo que recorre todo el ciclo). Hay planificación de sprint, backlog (trabajo pendiente), Scrum diario, revisión o demostración y retrospectiva. Ágil es un conjunto de valores; Scrum es uno de sus métodos. Otros: Kanban y programación extrema (XP).

## Código y ejemplos

Estructura mínima de un documento HTML bien formado: declara el tipo, el título (metadato) y el contenido visible.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mi primera pagina</title>
  </head>
  <body>
    <p>Bienvenida al sitio</p>
  </body>
</html>
```

Lista con viñetas y enlace con atributo `href`. Resultado: tres viñetas y un hipervínculo.

```html
<ul>
  <li>Planificar</li>
  <li>Disenar</li>
  <li>Construir</li>
</ul>
<a href="https://www.ibm.com">Ir a IBM</a>
```

Herencia y sustitución en CSS en línea. Resultado: el párrafo queda con sangría de 15px y la imagen con 40px, porque el hijo sustituye el valor del padre.

```html
<p style="margin-left: 15px;">
  Texto del informe
  <img src="jugador.png" alt="Foto del jugador" style="margin-left: 40px;">
</p>
```

Selectores de clase y de id en una hoja de estilo. Resultado: todos los elementos con `class="avisoCorto"` toman el color y el peso; solo el elemento con `id="descargo"` queda en negrita y cursiva.

```css
.avisoCorto {
  color: darkgreen;
  font-weight: bold;
}

#descargo {
  font-weight: bold;
  font-style: italic;
}
```

Suceso, escucha y manejador: al pulsar el botón se ejecuta la función y aparece una alerta.

```html
<button onclick="saludar()">Pulsar</button>
<script>
  function saludar() {
    alert("Hola, mundo");
  }
</script>
```

Búsqueda por id con `querySelector` para validar un campo vacío. Resultado: si el campo está vacío, se avisa al usuario.

```html
<section>
  <label>Ciudad <input id="ciudad"></label>
  <button onclick="validar()">Enviar</button>
</section>
<script>
  function validar() {
    const campo = document.querySelector('#ciudad');
    if (campo.value === '') {
      alert('Completa el campo Ciudad');
    }
  }
</script>
```

## Errores comunes
- Confundir Java con JavaScript: son lenguajes distintos y sin relación.
- Pensar que Scrum y ágil son lo mismo: ágil es un conjunto de valores; Scrum, un método.
- Dar por hecho que HTML5 funciona igual en todos los exploradores: cada fabricante lo implementa a su manera.
- Abusar de estilos en línea: obligan a modificar cada elemento por separado.
- Nombres de estilo CSS con espacios: no están permitidos.

## Herramientas
- **Exploradores:** Microsoft Edge, Mozilla Firefox, Google Chrome, Safari.
- **Marcos de código abierto:** React y Vue.js, para el manejo robusto de datos con JavaScript.
- **TypeScript:** lenguaje que se transpila a JavaScript.
- **querySelector:** función de JavaScript para localizar elementos del documento.

## Preguntas de repaso

1. ¿Qué tres desafíos de la transmisión de contenido resuelve el marcado y cómo?
   **Respuesta:** Incrustación (enlaza recursos en vez de incluirlos), cantidad (al ser texto usa menos ancho de banda) y apertura (es abierto y cualquier aplicación que interprete HTML puede representarlo).

2. ¿Qué significa que HTML sea un lenguaje declarativo?
   **Respuesta:** Que describe qué debe mostrarse, pero no cómo; el explorador decide cómo implementarlo siguiendo la especificación.

3. ¿Cuáles son las tres partes básicas de un estilo CSS y cómo se distinguen los selectores de clase e id?
   **Respuesta:** Selector, nombre y bloque de declaración con propiedades y valores. La clase se marca con punto y se aplica a muchos elementos; el id se marca con almohadilla y se aplica a uno solo.

4. ¿Cuál es la diferencia entre un lenguaje de script y uno compilado?
   **Respuesta:** El de script es interpretado y legible, se ejecuta línea a línea y se modifica y sube fácilmente, pero es más lento; el compilado se traduce antes a código de máquina y es más rápido, aunque cambiarlo es más difícil.

5. ¿Qué desventajas del enfoque en cascada intenta resolver la metodología ágil?
   **Respuesta:** Los ciclos largos, la poca interacción con el usuario y las pruebas aplazadas al final; lo hace con entregas en pequeños incrementos, como los sprints de Scrum.
