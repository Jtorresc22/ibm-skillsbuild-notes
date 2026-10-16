# Creación de sitios web dinámicos con JavaScript - M04

## Resumen
JavaScript permite que una página web reaccione a sucesos, modifique el DOM y gestione datos, tanto en el explorador como en el servidor. El curso recorre cinco bloques: uso de JavaScript con HTML, su modelo de programación (funcional y orientado a objetos), variables, funciones y expresiones, el manejo de datos con bases de datos y SQL, y Node.js con npm como entorno de servidor. Los datos y las bases de datos se tratan con MySQL como ejemplo.

## Conceptos clave
- **Página dinámica:** el usuario interactúa con el contenido (botones, formularios, vídeo).
- **Entorno de ejecución:** sistema y recursos donde corre un programa; el explorador y el servidor lo son.
- **DOM:** mapa de la estructura del HTML; JavaScript lo usa mediante interfaces como `getElementById`.
- **Suceso, escucha y manejador:** el cambio, el atributo que lo detecta y la función que responde.
- **Programación funcional y POO:** JavaScript combina ambas; sus funciones son de primera clase y también son objetos.
- **Miembros de un objeto:** constantes, propiedades, métodos y sucesos.
- **Herencia, instanciación, encapsulación:** pilares de la POO que el material explica.
- **Variables:** `const`, `var` y `let`; tipado débil con conversión implícita.
- **Expresiones y operadores:** `+` suma o concatena; `==` compara; `=` asigna.
- **Tipos de datos:** booleano, número, cadena, undefined y null.
- **CRUD y SQL:** crear, leer, actualizar y suprimir, ejecutados con DDL, DML y DQL.
- **Node.js y npm:** servidor web sin bloqueo escrito en JavaScript y su gestor de paquetes.
- **Biblioteca vs marco:** la biblioteca se llama bajo demanda; el marco se integra en todo el sitio.

## Detalle por tema

### Módulo 1 - La web dinámica: introducción a JavaScript
- JavaScript cambia contenido y estilos según sucesos, gestiona datos y da respuesta al usuario. El explorador descarga los archivos y ejecuta el código.
- Es un **lenguaje interpretado**: el explorador lee el código y ejecuta cada línea en orden mientras carga la página.
- Tres formas de incluirlo en HTML:
  - **En el cuerpo** con un elemento `script`: rápido para pruebas y demos, no recomendado en sitios activos, porque el HTML se carga de arriba abajo y el script puede ejecutarse antes de que existan los elementos que necesita.
  - **En la cabecera**: habitual, porque el código se carga antes de que se le llame.
  - **Desde un archivo externo** `.js` (texto plano) con el atributo `src`: la opción preferida; facilita la gestión del código y el trabajo en equipo (unos en JS, otros en HTML y CSS).
- El material recomienda añadir `type="text/javascript"` por legibilidad, aunque el explorador detecta el lenguaje por sí solo.
- **Modificar HTML:** si un elemento tiene un `id` (único y sensible a mayúsculas), `document.getElementById("id")` lo localiza y permite cambiar, por ejemplo, `style.color`.
- **DOM:** se compara con el mapa de un centro comercial. Sus interfaces permiten encontrar, cambiar, añadir y eliminar elementos, atributos y sucesos.
- **Sucesos:** cambios del sistema (dato modificado, interacción, error). Para responder se crean dos piezas: el **escucha de sucesos** (atributo HTML como `onclick`) y el **manejador** (función JavaScript que se declara con `function`, nombre, paréntesis y llaves).
- Escenario ampliado: un `div` con `onclick` que alterna el texto entre cursiva y normal, más una hoja de estilo con selector de elemento para color, grosor y tamaño.
- Advertencia: no todo lo que JavaScript permite conviene hacerlo; el texto parpadeante distrae y puede dañar a usuarios con fotosensibilidad.

### Módulo 2 - El modelo de programación JavaScript
- JavaScript no encaja en un único modelo: se considera principalmente **funcional** (las funciones hacen el trabajo, devuelven el control a quien las llamó y pueden enviarse a otras funciones) y muestra rasgos de **POO**.
- **Código espagueti:** en la programación procedimental antigua, el código no estaba estructurado, llevaba números de línea y usaba `goto` para saltar a otra línea. El exceso de rutas y bucles lo volvía inmanejable. De ahí surgieron los **objetos de código**: grupos reutilizables de código que guardan datos y hacen una función concreta.
- **Objetos de código:** se ilustran con un objeto de inicio de sesión que recibe usuario y contraseña (entrada), los compara con una base de datos y devuelve éxito o error (salida). Facilita la gestión, evita errores y permite reutilizar.
- **Miembros** (lo que permite almacenar datos o hacer trabajo):
  - *Constantes:* datos que no cambian durante la ejecución (p. ej., máximo de intentos de login).
  - *Propiedades:* datos que sí pueden cambiar (p. ej., la contraseña escrita).
  - *Métodos:* funciones dentro de un objeto (p. ej., verificar credenciales).
  - *Sucesos:* acciones que se realizan sobre el objeto o que este realiza.
- **Herencia:** un objeto nuevo reutiliza y amplía los miembros de otro (p. ej., añadir autenticación de dos factores, 2FA, al objeto de login). Analogías del material: plantilla de documento ampliada y clase "peces" con subtipos.
- **Instanciación:** crear una instancia, una versión individual de una clase. Ejemplo del material: tres instancias de una clase Login (usuario, empleado, cliente), cada una con su variable.
- **Encapsulación:** proteger partes del objeto (p. ej., el cifrado) y exponer otras. Analogía del cajero automático: las funciones públicas están disponibles y la verificación del PIN está oculta. En el ejemplo de la clase Login, el nombre de usuario y la contraseña solo se fijan al crear la instancia, y `setStatus` permite modificar `status` después.
- **Programación funcional:** una función recibe una entrada, trabaja y devuelve una salida; se **llama** para ejecutarla. Las funciones no están asociadas a objetos, los métodos sí. Las constantes y propiedades de una función solo existen mientras se ejecuta. En JavaScript, las funciones son objetos.

### Módulo 3 - Estructura de JavaScript
- **Variables:** guardan datos que pueden variar. En lenguajes **fuertemente tipados** (ejemplo del material: Java con `int`) hay que declarar el tipo y un valor de otro tipo produce error. JavaScript es **débilmente tipado**: deduce el tipo por contexto.
- **Declaración:**
  - `const`: valor inmutable durante la ejecución, de cualquier tipo.
  - `var`: valor modificable; JavaScript convierte el tipo según el contexto.
  - `let`: suele inicializarse al declarar y puede modificarse (p. ej., un contador).
- **Asignación:** se rellena la variable con el signo igual.
- **Funciones:** toman parámetros y devuelven un valor con `return`. Una función puede llamar a otra y **pasarle** datos (p. ej., validar el formato del correo antes de comprobar la contraseña).
- **Prototipos:** usar una función para heredar las características de otra y ampliarla; es una de las formas en que JavaScript muestra rasgos de POO.
- **Funciones de primera clase:** se tratan como cualquier otra variable; se pasan como argumento, se devuelven desde otra función y se asignan a una variable. Ejemplo del material: asignar a una variable una función que calcula el total del carrito.
- **Expresiones y operadores:** el operador realiza la operación y la expresión es la sentencia completa. Con `+`, dos cadenas se **concatenan** y dos números se suman; JavaScript elige en ejecución según los tipos (**conversión de tipo implícito**).
- **Comparación:** el signo igual simple asigna, por lo que para comparar se usa el doble (`==`).
- **Sucesos (resumen):** el escucha vigila el cambio (atributo `onclick` en un botón) y el manejador responde (función que, p. ej., muestra un aviso de éxito).

### Módulo 4 - Interactuar con los datos
- **Datos:** información en un formato que el ordenador puede almacenar y procesar (entrada, proceso, salida).
- **Usos en un sitio de compras:** búsqueda, sugerencias (a partir de compras históricas), autenticación, geolocalización (vía datos del ISP) y cálculos (total con envío e impuestos).
- **Fuentes:** *datos generados por el usuario* (ratón, voz, teclado) y *bases de datos* (colección estructurada, normalmente en un servidor).
- **Tipos de datos:** atributo que indica cómo interpretar un valor; validar el formato esperado evita errores (p. ej., una fecha DD/MM/AAAA). Cada lenguaje tiene sus **tipos primitivos**. Los de JavaScript que cita el resumen del material: booleano (verdadero/falso), número, cadena, undefined (sin valor aún) y null (solo el valor Null). La tabla completa del material es una imagen y no se recoge aquí (no cubierto el detalle de la tabla).
- **Bases de datos:** formadas por una o más **tablas** relacionadas (filas = **registros**, columnas = campos). Una **entidad** es un elemento sobre el que se guardan datos (p. ej., "bebida" con nombre, tipo, precio y temporada).
- **CRUD:** crear (añadir), leer (uno, varios o todos), actualizar (editar) y suprimir (eliminar).
- **SQL:** lenguaje estándar (mantenido por ISO, con variaciones de sintaxis según el motor) para gestionar bases de datos. Los ejemplos usan **MySQL**.
- **Sintaxis:**
  - Cada sentencia empieza con un mandato y termina con `;`, por lo que puede ocupar varias líneas.
  - No distingue mayúsculas, pero la buena práctica es escribir las palabras clave en mayúsculas.
  - Tablas con varias palabras: subrayado (`movie_info`). Columnas: bicapitalización (camelCase).
- **Categorías de mandatos:**
  - *DDL (definición):* `CREATE`, `ALTER`, `DROP`.
  - *DML (manipulación):* `INSERT`, `UPDATE`, `DELETE`.
  - *DQL (consulta):* `SELECT`.
- **Caso de ejemplo (base de películas):** crear base y tabla, insertar filas, leer con `SELECT` (`*` = todas las columnas; `WHERE` filtra) y corregir un dato con `UPDATE`. Se puede trabajar desde una interfaz de línea de mandatos (CLI; Terminal en Mac, línea de comandos en Windows) o una GUI.
- **`WHERE` en `UPDATE`:** define qué registros cambian; sin ella se modifican todos.

### Módulo 5 - Ejecución: introducción a Node.js
- **Servidor web:** software que escucha solicitudes y entrega páginas. Cliente y servidor dependen uno del otro; el cliente inicia el trabajo y el servidor debe estar siempre a la escucha.
- **Node.js:** entorno de ejecución basado en JavaScript, gratuito y de **código abierto**, que corre en servidores.
- **Flujo de una solicitud:**
  1. El usuario escribe una dirección y el explorador envía la solicitud (actividad del lado del cliente).
  2. El **DNS** convierte la dirección web en una **dirección IP** (código numérico de cuatro partes).
  3. La solicitud llega al servidor, que escucha y responde enviando la página (actividad del lado del servidor).
- **Protocolo y puerto:** el servidor solo responde a solicitudes enviadas con un protocolo (HTTP o HTTPS) a un puerto concreto: 80 para HTTP y 443 para HTTPS. Sin puertos abiertos no acepta solicitudes.
- **Cumplir una solicitud:** se devuelven texto, imágenes y código al explorador; a veces ese código pide más datos, lo que genera varios **viajes de ida y vuelta**.
- **Ventajas de Node.js:** está escrito en JavaScript (un solo lenguaje en cliente y servidor); es **sin bloqueo** (delega tareas lentas, como consultar una base de datos, y sigue atendiendo solicitudes); es de código abierto y tiene cientos de bibliotecas.
- **npm:** gestor de paquetes que busca, descarga e instala software de su catálogo, permite compartir y restringir código, gestionar versiones y dependencias, y crear organizaciones. Requiere tener Node.js instalado; no es obligatorio, pero el material lo presenta como primer paso común al preparar un sistema.
- **Bibliotecas y marcos:**
  - Semejanzas: contienen código JavaScript para tareas concretas, se integran en el código propio, son de código abierto y se instalan con npm; no ejecutan un sitio por sí solos.
  - Diferencias: la biblioteca tiene función más limitada y se llama bajo demanda; el marco añade capacidades que JavaScript nativo no tiene y se integra en todo el sitio, cambiando su funcionamiento. Los marcos pueden tener bibliotecas como **dependencia**; al revés no.
  - Ejemplos citados: jQuery (biblioteca); React, Vue.js y Angular (marcos).

## Código y ejemplos

Cargar un script externo desde la cabecera (carga el archivo `app.js` antes del cuerpo).
```html
<head>
  <script src="app.js"></script>
</head>
```

Cambiar el color de un elemento por su id. Resultado: el segundo párrafo se muestra en azul al cargar la página.
```html
<body>
  <h1>Cambiar estilos con JavaScript</h1>
  <p id="intro">Primer párrafo sin cambios.</p>
  <p id="nota">Este párrafo se pondrá azul.</p>

  <script>
    // Busca el elemento con id "nota" y cambia su color
    document.getElementById("nota").style.color = "blue";
  </script>
</body>
```

Escucha y manejador de sucesos. Resultado: cada clic alterna el texto del recuadro entre negrita y peso normal.
```html
<div id="caja" onclick="alternarPeso()">Haz clic para alternar el peso de la fuente.</div>

<script>
  // Manejador: se ejecuta cuando el usuario hace clic en el div
  function alternarPeso() {
    const caja = document.getElementById("caja");
    if (caja.style.fontWeight !== "bold") {
      caja.style.fontWeight = "bold";
    } else {
      caja.style.fontWeight = "normal";
    }
  }
</script>
```

Variables, concatenación y comparación. Resultado: muestra "Hola, Marta" y luego el aviso "Acceso permitido".
```js
const maxIntentos = 3;            // const: no cambia
let intentos = 0;                 // let: puede modificarse
var saludo = "Hola, ";            // var: modificable

const mensaje = saludo + "Marta"; // + concatena cadenas
console.log(mensaje);

const usuarioBD = "marta01";
const usuarioForm = "marta01";
if (usuarioBD == usuarioForm) {   // == compara; = asigna
  alert("Acceso permitido");
}
```

Función de primera clase asignada a una variable. Resultado: `totalCarrito([10, 25], 3, 5, 8)` devuelve "El total es 35".
```js
const totalCarrito = function (precios, impuesto, envio, descuento) {
  let suma = 0;
  for (let i = 0; i < precios.length; i++) {
    suma = suma + precios[i];
  }
  suma = suma + impuesto + envio - descuento;
  return "El total es " + suma;
};

console.log(totalCarrito([10, 25], 3, 5, 8));
```

Función que llama a otra y le pasa un dato (validación en dos pasos).
```js
function validarCorreo(usuario) {
  return usuario.includes("@");
}

function comprobarAcceso(usuario, clave) {
  if (!validarCorreo(usuario)) {
    return "No se ha podido verificar.";
  }
  // Aquí iría la comprobación real de la clave
  return clave.length > 0 ? "Verificado" : "No se ha podido verificar.";
}
```

Escucha en un botón y su manejador.
```html
<button onclick="avisar()">Enviar</button>
<script>
  function avisar() {
    alert("Operación realizada");
  }
</script>
```

Crear base y tabla, e insertar filas. Resultado: una base `libreria` con una tabla de tres libros.
```sql
CREATE DATABASE libreria;

CREATE TABLE book_info (
  bookNum INT,
  bookTitle VARCHAR(100),
  publishYear YEAR,
  authorLastName VARCHAR(50),
  pages INT
);

INSERT INTO book_info (bookNum, bookTitle, publishYear, authorLastName, pages)
VALUES
  (1, 'Cuentos de otoño', 1998, 'Rivas', 210),
  (2, 'El faro', 2005, 'Soto', 180),
  (3, 'Mapas', 2015, 'Lara', 320);
```

Leer, filtrar y actualizar. Resultado: la primera consulta devuelve todo; la segunda, solo títulos y páginas de libros con más de 200 páginas; el `UPDATE` corrige un año solo en ese libro.
```sql
SELECT * FROM book_info;

SELECT bookTitle, pages FROM book_info WHERE pages > 200;

UPDATE book_info
SET publishYear = 2006
WHERE bookTitle = 'El faro';
```

## Errores comunes
- Incluir el `script` en el cuerpo en sitios activos: puede ejecutarse antes de que la página cargue lo que necesita.
- Usar `=` para comparar: asigna; la comparación requiere `==`.
- Omitir `WHERE` en un `UPDATE`: cambia todos los registros de la tabla.
- Dar a un elemento un `id` repetido: el `id` debe ser único.
- Olvidar el `;` final en SQL: MySQL lo usa para detectar el fin de la sentencia.
- Escribir datos que no respetan el tipo o formato esperado (p. ej., una fecha en palabras): provoca error.
- Abusar de efectos dinámicos como el texto parpadeante: perjudica la experiencia y a usuarios sensibles a la luz.
- Material de origen: los ejemplos de código del material contienen erratas (etiquetas mal escritas, sentencias SQL incompletas, nombre de columna inconsistente en un `SELECT`); en esta nota se han reescrito corregidos.

## Herramientas
- **Editor de texto o IDE:** para crear archivos `.js`.
- **Node.js:** entorno de ejecución de JavaScript en servidor.
- **npm (gestor de paquetes de Node):** instala bibliotecas y marcos.
- **MySQL:** sistema de gestión de bases de datos de código abierto.
- **CLI y GUI:** formas de ejecutar sentencias MySQL (línea de mandatos o interfaz gráfica).
- **jQuery, React, Vue.js, Angular:** biblioteca y marcos citados como ejemplos.

## Preguntas de repaso

1. ¿Por qué se prefiere cargar JavaScript desde un archivo externo y qué atributo se usa?
   **Respuesta:** porque facilita la gestión del código y el trabajo en equipo (JS por un lado, HTML y CSS por otro). Se referencia en la cabecera con el elemento `script` y el atributo `src`.

2. ¿Qué diferencia hay entre `const`, `var` y `let`?
   **Respuesta:** `const` guarda un valor inmutable; `var` guarda un valor modificable y JavaScript ajusta su tipo según el contexto; `let` se suele inicializar al declararla y también puede modificarse.

3. Explica herencia, instanciación y encapsulación.
   **Respuesta:** la herencia permite que un objeto nuevo reutilice y amplíe los miembros de otro; la instanciación es crear una instancia individual de una clase; la encapsulación protege ciertos aspectos de un objeto y expone otros para que se puedan modificar.

4. ¿Qué hacen los mandatos DDL, DML y DQL de SQL? Da un ejemplo de cada uno.
   **Respuesta:** DDL define bases y tablas (`CREATE`, `ALTER`, `DROP`); DML modifica los datos de las tablas (`INSERT`, `UPDATE`, `DELETE`); DQL consulta datos (`SELECT`).

5. ¿Qué significa que Node.js sea "sin bloqueo" y por qué importa?
   **Respuesta:** delega las tareas lentas en segundo plano (como consultar una base de datos) a otra aplicación, que avisa al servidor al terminar. Así el servidor queda libre para aceptar y cumplir otras solicitudes en lugar de quedar bloqueado esperando.
