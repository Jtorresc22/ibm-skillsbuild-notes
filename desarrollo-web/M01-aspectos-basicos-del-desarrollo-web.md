# Aspectos básicos del desarrollo web - M01

## Resumen
Todo ordenador cumple cuatro funciones (entrada, proceso, salida y almacenamiento) apoyándose en hardware y software, y solo entiende código binario; la abstracción y los traductores (compilador e intérprete) permiten programar en lenguajes legibles. El desarrollo web abarca planificar, codificar, probar, publicar y mantener sitios, con trabajo del lado del cliente (front-end) y del lado del servidor (back-end). Por debajo, Internet (la red) transporta lo que la World Wide Web (los sitios) muestra, y la nube aporta alojamiento, datos y escalado bajo demanda.

## Conceptos clave
- **Funciones básicas del ordenador:** entrada, proceso, salida, almacenamiento.
- **Código binario (o de máquina):** ceros y unos; único lenguaje que entiende el ordenador.
- **Hardware / software / sistema operativo:** componentes físicos, instrucciones y el gestor que los coordina.
- **Abstracción:** ocultar la complejidad de la máquina para poder dar instrucciones sin conocer sus detalles.
- **Compilador / intérprete:** traducen el código fuente a código de máquina (todo de una vez / línea a línea).
- **Sintaxis:** estructura y reglas de un lenguaje de programación.
- **Desarrollo web vs. diseño web:** construir y mantener el sitio vs. cuidar cómo se presenta al usuario.
- **Lado del cliente / lado del servidor:** qué se ejecuta en el dispositivo del usuario y qué en los servidores.
- **Front-end:** HTML (estructura), CSS (estilo), JavaScript (interacción).
- **Back-end:** servidores, aplicaciones y bases de datos; JavaScript, Python, Java.
- **Internet vs. World Wide Web:** infraestructura de red vs. conjunto de sitios web.
- **DNS, dirección IP, TCP:** traducción de nombres, direccionamiento y fragmentación de datos.
- **Computación en la nube:** servidores especializados por función, usados solo cuando se necesitan.

## Detalle por tema

### Cómo funciona un ordenador
- **Entrada:** información que recibe el sistema (teclado, ratón, pantalla táctil, micrófono, sensores). Se convierte a código binario para procesarla o guardarla. Los desarrolladores crean las interfaces por las que el usuario aporta datos.
- **Proceso:** serie de acciones que transforman los datos recibidos (números, letras, órdenes simples); son sobre todo operaciones lógicas. Los programas de los desarrolladores dictan qué hacer con ellos.
- **Salida:** resultado útil de esa transformación (texto, números, fotos, vídeo, audio) mostrado en pantallas, altavoces o impresoras. Los dispositivos de salida decodifican el código de máquina a un formato comprensible.
- **Almacenamiento a corto plazo (memoria volátil, RAM):** guarda datos mientras el dispositivo funciona; por ejemplo, los datos de un pedido hasta que el usuario lo envía. Suele gestionarlo el explorador.
- **Almacenamiento a largo plazo:** conserva datos tras apagar el equipo (unidades SSD o HDD). Los sitios web crean **cookies**, pequeños archivos con datos del usuario (última visita, tiempo hasta pedir de nuevo el inicio de sesión) que persisten entre **sesiones** (bloque continuo de tiempo en un sitio).
- **Hardware:** componentes físicos (CPU, RAM). Los **dispositivos de E/S** (teclado, micrófono, ratón) recogen entradas y entregan salidas.
- **Software:** el **sistema operativo** (Linux, Windows, Android, macOS, iOS) gestiona hardware y software y evita tener que conocer el código de máquina. Las demás aplicaciones (exploradores, procesadores de texto, editores de imágenes) amplían las tareas.
- **Relación con la web:** los exploradores web (Chrome, Firefox, Internet Explorer) cambiaron la forma de acceder a programas, pero sin los sitios y aplicaciones que escriben los desarrolladores tienen poca utilidad (analogía: coche y conductor).
- **Aplicaciones web:** híbrido entre programa y página web. Pueden correr en el explorador o empaquetarse en un **wrapper** para ofrecerlas como app móvil con el mismo código. Frente a una página, tienen más acceso a recursos del sistema (almacenamiento, sistema de archivos, procesador gráfico).

### Hablemos del código
- **Abstracción:** igual que se conduce sin saber de mecánica, los lenguajes de programación ocultan la complejidad de la máquina. Los primeros programas se escribían en código de máquina y ensamblador (bajo nivel); con el tiempo los lenguajes se acercaron al lenguaje natural.
- **Lenguajes de máquina:** formados por **bits** (dos estados: encendido/apagado, sí/no); combinados en patrones representan mucha información. La CPU los interpreta directamente. Hoy casi no se usan para programar.
- **Lenguajes compilados:** se usan para sistemas operativos, controladores y gestión de memoria o transferencia de datos; se consideran de bajo nivel por su cercanía al hardware. Requieren un **compilador** (invento de mediados del siglo XX) que convierte el **código fuente** en código de máquina. La compilación suele ser unidireccional: para cambiar algo hay que editar el código fuente y recompilar. El programa completo se carga en memoria. Ejemplos: C, Java, C#.
- **Lenguajes interpretados:** los más abstractos; son **autodescriptivos** (la sintaxis indica qué hace el código). Un **intérprete** lee y ejecuta cada línea de forma independiente en **tiempo de ejecución** (código activo en memoria en un momento dado); qué queda en memoria depende de cómo se escriba el programa. Ejemplos: Python, JavaScript.
- **Analogía de interruptores:** cada interruptor es un bit (0 apagado, 1 encendido). Con uno hay 2 estados; con dos hay 4 (apagada, 33 %, 66 %, máxima potencia). Más interruptores, exponencialmente más estados. Las tarjetas perforadas funcionaban así: agujero = Sí, sin agujero = No, una tarjeta por línea de código, leídas en pila hasta que el sistema almacenaba todas las instrucciones.
- **Conversión de lenguaje:**
  1. El traductor (compilador o intérprete) verifica la sintaxis y las reglas; si hay un error se detiene e informa de qué es y dónde ocurre.
  2. Convierte el código a lenguaje de máquina, el único que la CPU puede usar.
  3. El sistema operativo abre el código traducido, lee las instrucciones y las ejecuta.
- Todo código acaba como lenguaje de máquina, ya sea por compilador o por intérprete. HTML y CSS se citan en el material como lenguajes legibles gracias a este proceso.

### Qué es el desarrollo web
- **Desarrollo web:** crear y mantener páginas y sitios: código de diseño, fuentes, colores, interactividad, y también bases de datos, servidores, red, API y software del lado del servidor.
- **Diseño web:** cómo se presentan los elementos al usuario (información fácil de encontrar, colores agradables, espacio negativo adecuado, accesibilidad). Los roles de desarrollador y diseñador se solapan pero cada uno aporta algo propio.
- **Importancia:** el uso de Internet creció a casi 5 mil millones de usuarios en 2022; sin desarrolladores no habría sitios informativos, redes sociales ni **comercio electrónico**.
- **Sitio web:** colección de páginas bajo un mismo **nombre de dominio**. Una **página web** muestra texto, imágenes, vídeo y otros elementos, descritos en archivos de código: diseño, contenido y multimedia, estilo, e interacciones (enlaces, botones, inicio de sesión, autenticación).
- **Dominio y URL:** el dominio es el nombre del sitio; la **URL** es la dirección completa (los exploradores suelen completar www y https://). Cada página tiene su propia URL con el mismo dominio; la estructura de navegación y el **menú de navegación** enlazan las páginas.
- **Explorador:** pide los archivos al **host del sitio web** (proveedor de alojamiento), los interpreta y los muestra como **interfaz de usuario (UI)**.
- **Servidor web:** ordenador (o red de ordenadores) diseñado para alojar y servir páginas a muchos visitantes (analogía de la galería de arte).
- **Fases del proceso:**
  - *Planificación y diseño:* se definen **requisitos** con diseñadores y partes interesadas; los **wireframes** muestran posición, tamaño y separación de elementos y su aspecto en distintas pantallas.
  - *Codificación:* se programan los archivos a partir de wireframes y requisitos. Si algo no es viable, se vuelve al diseñador o director de proyecto: es un **proceso iterativo**. También se compra y registra el dominio y se configura el alojamiento (proveedor o servidores propios).
  - *Prueba y publicación:* se verifica que sea **funcional** (enlaces, botones, interacciones, requisitos) y **accesible** (usuarios con discapacidad auditiva o visual, entre otros). Se prueba en un **sitio de transferencia**, copia idéntica al sitio activo pero solo accesible al equipo; después un equipo de publicación **envía** los archivos al sitio activo, evitando **interrupciones** (algo que funcionaba deja de hacerlo o desaparece).
  - *Mantenimiento:* cambios simples de contenido o imágenes, hasta actualizaciones importantes de funcionalidad.
- **Lado del cliente:** se ejecuta en el dispositivo del usuario; representa diseños y envía solicitudes, maneja elementos visuales (colores, tipografía), responde a interacciones (botones, validación de formularios) e intercambia datos con el servidor.
- **Lado del servidor:** entrega contenido dinámico según acciones del usuario o datos de una base de datos; almacena, gestiona y sirve datos; autentica el inicio de sesión; recibe y envía datos al cliente; ejecuta procesos pesados y devuelve resultados.
- Ambos lados cooperan: por ejemplo, el servidor escucha solicitudes de datos bancarios y el cliente las pide o usa el software del servidor para recuperarlos.

### Desarrollo front-end
- Se centra en lo que el usuario ve y con lo que interactúa; el código corre en su dispositivo. Abarca diseño y elementos visuales, interacciones que recogen entradas, experiencia de usuario y accesibilidad, uso en varios dispositivos y correcta presentación de multimedia. Los **estilos** son reglas de formato que indican cómo mostrar cada tipo de elemento.
- **Listo para móviles:** el **diseño web reactivo** agrupa técnicas para adaptarse al tamaño y orientación de pantalla (horizontal/vertical) y al tipo de pantalla (táctil: evitar entradas que exijan teclado físico, touchpad o ratón). Muchos **marcos** (React, Vue.js, Bootstrap) lo admiten; un marco es un paquete de software con interfaz y herramientas de datos integradas.
- **SEO:** los motores de búsqueda **rastrean la web** para crear un índice y ordenan los sitios con algoritmos (velocidad, compatibilidad móvil, accesibilidad). Los desarrolladores añaden **metadatos** en la cabecera que deben coincidir con el contenido del cuerpo.
- **Accesibilidad:** un sitio es accesible si ofrece información a lectores de pantalla (texto descriptivo de imágenes), se adapta a discapacidades físicas (modo oscuro, alto contraste) y es reactivo (navegación táctil).
- **Desafíos:** cumplir demandas técnicas bajo restricciones de tecnología, estilo, lenguajes y presupuesto; mantener compatibilidad entre exploradores, versiones y plataformas con estándares distintos; y prever una **degradación adecuada** (funcionamiento limitado en versiones antiguas).
- **Lenguajes:** HTML (estructura, como los cimientos de una casa), CSS (colores, fondos, animaciones, decoración) y JavaScript (ventanas emergentes, galerías dinámicas, contenido personalizado).

### Desarrollo back-end
- Es lo que ocurre "tras bambalinas": servidores (envían y reciben datos), aplicaciones (procesan solicitudes y respuestas del front-end) y bases de datos (almacenan y organizan datos). Su trabajo es que se comuniquen entre sí con fluidez y rapidez.
- El código corre en el servidor; se centra en lógica, integración y gestión de datos; procesa y almacena datos de los usuarios; y vela por seguridad, integridad de datos y reacción del servidor.
- Cuando el servidor recibe una solicitud devuelve archivos, que el explorador interpreta y muestra según el código front-end.
- **Lenguajes:** la elección depende del proyecto y de lo que el desarrollador domine.
  - *JavaScript:* scripts del lado del servidor, páginas dinámicas, formularios, operaciones de base de datos.
  - *Python:* versátil; sitios interactivos, comunicación con bases de datos, procesamiento de datos, envío y recepción desde servidores; por ejemplo, comprobar usuario y contraseña en un inicio de sesión.
  - *Java:* aplicaciones y servidores web, apps con mucho uso de datos y seguridad, streaming multimedia, motores de recomendación y aplicaciones con IA.

### Una red de redes
- **Internet vs. World Wide Web:** la Web son los sitios web (los lugares de una ciudad); Internet es la red de ordenadores y servidores que da la infraestructura (las calles).
- **Cómo funciona Internet** (analogía del viaje en tren):
  1. *Conectarse:* el **módem** recibe la señal del ISP y la convierte a un formato comprensible; el **router** gestiona la información y reparte la conexión entre los dispositivos.
  2. *Pedir destino:* al escribir una URL, la solicitud va al **ISP** (que conecta con muchas redes y entrega los datos usando protocolos estándar), el cual usa un **DNS** para convertir la URL en una **dirección IP** numérica (formato nnn.nnn.nnn.nnn, 32 bits en campos de 8 bits). Sin DNS habría que recordar IP en lugar de nombres.
  3. *Preparar el envío:* el explorador divide la solicitud en fragmentos con **TCP**; TCP e IP son los dos estándares básicos de Internet.
  4. *Viaje:* el mensaje toma la ruta más rápida por la red de redes.
- **Nube:** al principio un servidor sostenía pocos sitios (incluso bajo un escritorio); luego se conectaron cientos o miles en **granjas de servidores**. La **computación en la nube** separa las funciones de un servidor en servidores dedicados (almacenar y leer/escribir datos, procesar, potencia de cálculo, redes, software especializado), de modo que se usan solo los recursos necesarios.
- **Qué aporta al desarrollador web:**
  - *Alojamiento:* red mundial de ordenadores (proveedores como IBM, Amazon, Google) que hace los sitios rápidos y disponibles; ofrecen también certificados de seguridad, bases de datos, alojamiento de dominios e IA.
  - *Distribución de cargas:* parte de la lógica vive en la nube (por ejemplo, obtener datos de otra entidad financiera) y el sitio la invoca mediante una **llamada de API**; así el sitio pesa menos, carga más rápido y la funcionalidad se actualiza sin cambiar la app.
  - *Datos y blobs:* bases de datos de código abierto o propietarias, y almacenamiento de **blobs** (archivos grandes con datos binarios: imágenes, vídeos, documentos) optimizado para moverlos entre servidores y usuarios.
  - *Escalado:* se paga solo por la capacidad usada y se amplía o reduce automáticamente según la demanda (por ejemplo, un evento deportivo en directo), manteniendo rendimiento y disponibilidad.

## Herramientas
- **Compilador / intérprete:** traductores de código fuente a código de máquina.
- **Explorador web:** interpreta los archivos del sitio y muestra la interfaz.
- **Wireframes:** diagramas de diseño para guiar la codificación.
- **Sitio de transferencia:** entorno idéntico al activo para probar antes de publicar.
- **Wrapper:** empaqueta el código de una aplicación web para entregarla como app de teléfono.
- **Marcos (React, Vue.js, Bootstrap):** facilitan el diseño reactivo.
- **Proveedores de nube:** alojamiento, bases de datos, almacenamiento de blobs y servicios de IA.

## Preguntas de repaso

1. ¿Cuáles son las cuatro funciones básicas de un ordenador y qué papel tiene el código binario en ellas?
   **Respuesta:** Entrada, proceso, salida y almacenamiento. Los datos de entrada se convierten a código binario (ceros y unos), único lenguaje que el ordenador entiende, para procesarlos o guardarlos; los dispositivos de salida lo decodifican de nuevo a un formato legible.

2. ¿En qué se diferencia un lenguaje compilado de uno interpretado?
   **Respuesta:** El compilado pasa por un compilador que traduce todo el código fuente a código de máquina antes de ejecutarse (y para cambiarlo hay que recompilar); el interpretado lo lee un intérprete línea por línea durante el tiempo de ejecución. C, Java y C# son compilados; Python y JavaScript, interpretados.

3. ¿Qué se hace en cada fase del desarrollo de un sitio web y por qué se usa un sitio de transferencia?
   **Respuesta:** Planificación y diseño (requisitos y wireframes), codificación, prueba (funcionalidad y accesibilidad), publicación y mantenimiento. El sitio de transferencia es una copia idéntica del activo, solo accesible al equipo, donde se prueba todo para evitar interrupciones al publicar.

4. ¿Qué diferencia hay entre los procesos del lado del cliente y del lado del servidor, y qué lenguajes usa cada tipo de desarrollador?
   **Respuesta:** Los del cliente se ejecutan en el dispositivo del usuario (representar páginas, responder a interacciones, validar formularios); los del servidor se ejecutan en los servidores (almacenar datos, autenticar, ejecutar procesos pesados). El front-end usa HTML, CSS y JavaScript; el back-end, JavaScript, Python y Java.

5. ¿Qué ocurre desde que se escribe una URL hasta que se recibe la página, y qué ventajas ofrece la nube al desarrollador?
   **Respuesta:** La solicitud sale por el módem/router al ISP, que usa DNS para traducir la URL a una dirección IP; TCP fragmenta los datos y estos viajan por la ruta más rápida. La nube permite alojar con alcance mundial, distribuir cargas mediante llamadas de API, almacenar datos y blobs, y escalar pagando solo lo usado.
