# Prueba y despliegue de sitios web - M05

## Resumen
Este documento recorre el ciclo completo de entrega de un sitio web: cómo se prueba (tipos de pruebas y áreas a cubrir), cómo se controlan los cambios del código con un sistema de control de versiones y cómo se publica y despliega. Explica la entrega y el despliegue continuos, DevOps y su ciclo de vida, la entrega de contenido a todos los dispositivos (diseño reactivo, aplicaciones web) y las herramientas de pruebas y despliegue. Cierra con el despliegue en la nube y los contenedores.

## Conceptos clave
- **Error (bug):** defecto en el código que hace que un sitio o una función falle o se comporte de forma inesperada.
- **Entorno de pruebas:** copia separada del sitio activo, accesible solo para desarrolladores y QA.
- **Entorno de transferencia (staging):** réplica del sitio activo donde se detectan problemas de última hora antes de publicar.
- **Control de versiones:** sistema que registra quién, qué, dónde, cuándo y por qué se cambió el código.
- **Repositorio de código:** almacén de las versiones de los archivos; el repositorio de la organización es el repositorio remoto.
- **Entrega continua / despliegue continuo:** automatizan, respectivamente, el paso de código al entorno de pruebas y su publicación automática en producción.
- **DevOps:** método que une negocio, desarrollo y operaciones de TI para responder antes a los usuarios.
- **Diseño reactivo:** el sitio adapta su aspecto y comportamiento al tamaño y orientación de la pantalla.
- **Aplicación web / wrapper de aplicaciones:** sitio web empaquetado como app descargable.
- **Contenedor y máquina virtual:** dos formas de crear entornos de ejecución aislados.
- **Latencia y réplica:** retardo de una señal según la distancia, y copia del sitio en servidores de varias regiones para reducirlo.
- **Microservicio:** parte autónoma de una aplicación con una única función.

## Detalle por tema

### Módulo 1: Prueba de un sitio web
**Por qué se prueba.** Se prueban tanto el código como la experiencia de usuario. A diferencia de una aplicación de escritorio, el sitio puede usarse en pantallas, dispositivos de entrada y tamaños muy distintos. Las pruebas tempranas reducen costes y evitan problemas de diseño, arquitectura, funcionalidad, seguridad y escalabilidad. No todos los defectos son errores de código: también los hay de diseño y de experiencia.

**Tipos de pruebas.**

| Tipo | Qué comprueba |
|---|---|
| Aceptación | Que todo el sitio (cliente y servidor) funciona como se esperaba; la hacen usuarios al final, antes del lanzamiento |
| Integración | Que los componentes funcionan juntos (por ejemplo, llamadas API del cliente y respuesta correcta del servidor) |
| Unidad | Que una característica concreta, la unidad testeable más pequeña, se comporta como debe (por ejemplo, un menú desplegable) |
| Funcionales | Comportamiento en escenarios reales según los requisitos iniciales; una forma habitual son las pruebas de caja cerrada |
| Rendimiento | Comportamiento bajo distintos niveles de estrés; las pruebas de carga miden el rendimiento en condiciones reales (nº de solicitudes) |
| Regresión | Que una función nueva o modificada no rompa lo existente; si lo hace, hay un error de regresión |
| Estrés | Como rendimiento, pero con carga extrema, para ver cuánto aguanta antes de fallar |
| Usabilidad | Con qué facilidad un usuario completa tareas en el sitio |

**Áreas a probar.**
- **Interfaz de usuario:** ubicación de elementos, interacción entre ellos, colores y fuentes (también sus cambios al interactuar), todo según el diseño y los requisitos.
- **Diseño reactivo:** misma experiencia en todos los dispositivos. Incluye probar distintas orientaciones del dispositivo mediante los ángulos alfa (eje Z), beta (eje X) y gamma (eje Y).
- **Código:** propio y de código abierto (que también puede tener errores); debe ser seguro. Ejemplo del material: comprobar que la contraseña de un login no queda expuesta en el código.
- **API:** que el envío y la devolución de datos entre cliente y servidor sean seguros y precisos, y que usuarios malintencionados no eludan la seguridad.
- **Bases de datos:** el desarrollador responde de que funcione bien con el sitio aunque la diseñe un administrador de bases de datos. Si el servidor web y la base de datos están en regiones distintas de la nube, el rendimiento empeora.

**Proceso de prueba.**
1. Definir el entorno de pruebas.
2. Desarrollar casos de prueba (serie de pasos para verificar una función: layout, enlaces, buscador...).
3. Escribir y ejecutar scripts de automatización (se escriben en un lenguaje de programación y se ejecutan con herramientas como IBM UrbanCode o Jenkins).
4. Analizar resultados: comparar lo esperado con lo real e identificar discrepancias (por ejemplo, volcando datos a una hoja de cálculo).
5. Enviar informes de error: pasos para reproducir, comportamiento esperado y real, y opcionalmente capturas o vídeos, dirigido a un jefe de proyecto o desarrollador sénior.

**Automatización.** Ahorra tiempo en tareas repetitivas, aumenta precisión al quitar el error humano, detecta problemas no evidentes (rendimiento, seguridad), permite probar varios tamaños de pantalla y evaluar ideas (por ejemplo, mover el login a la nube) sin tocar el código real.

### Módulo 2: Seguimiento y gestión de cambios del código
**Idea.** Un equipo grande necesita registrar los cambios a lo largo del tiempo. El material lo compara con un cuaderno compartido con un registro de cambios. Uno de los primeros sistemas fue el **SCCS** (Sistema de control de códigos fuente): guardaba todas las versiones en un solo archivo, marcaba número de versión, fecha y autor y usaba un registro delta de cada modificación.

**Características de los sistemas actuales.**
- **Repositorio de código:** guarda las versiones de los archivos (además del servidor web donde se aloja el sitio).
- **Herramientas de colaboración:** trabajo simultáneo en los mismos archivos, comentarios, documentación (archivo readme con descripción, instalación y ayuda), gestión de proyectos y chat.
- **Despliegue del código:** publicar en el entorno activo, previo paso por un entorno de transferencia. Muchos sistemas incluyen despliegue continuo: prueban automáticamente y, si pasan, publican.

**Flujo de trabajo típico** (analogía de tres chefs con un documento principal): se parte de un archivo principal, cada persona trabaja en su copia, y al final se decide qué cambios aceptar. Si solo uno cambia algo y es una mejora, se acepta; si cambios distintos no chocan, se fusionan; si varios modifican lo mismo de forma distinta, hay un **conflicto** y el equipo elige cuál conservar.

Pasos en un sistema de control de versiones:
1. **Clonar** el repositorio remoto a la máquina local.
2. **Captar (fetch)** los últimos cambios de los archivos principales.
3. **Confirmar (commit):** registrar los cambios hechos desde el último commit, con un mensaje breve; sirve para ver qué cambió y deshacer problemas.
4. **Solicitud de extracción (pull request):** proponer los cambios; el equipo los revisa y acepta, rechaza o pide ajustes. Si se aceptan, se fusionan en los archivos principales.
5. **Push:** subir la copia local al repositorio remoto.

Distintos sistemas pueden usar otros términos, pero los pasos son equivalentes.

### Módulo 3: Entrega de un sitio web a los usuarios
**Publicar** es poner el sitio a disposición de sus usuarios (que no siempre son el público general; puede ser solo personal de una empresa). Hacen falta: contenido (los requisitos), usuarios definidos y tecnología de alojamiento (servidor propio o proveedor de nube).

**Fases de la publicación.**
- **Preparación:** elegir dónde alojar, reservar y configurar el nombre de dominio, aplicar medidas de seguridad específicas (por ejemplo, un certificado de sitio para comercio electrónico).
- **Configuración:** reunir todos los archivos y probar en el entorno de transferencia.
- **Entrega:** copiar archivos y valores de configuración desde transferencia al destino final y habilitar funciones (dominio, comercio electrónico).

**De la publicación puntual al despliegue frecuente.** Tradicionalmente se publicaba el sitio completo en una fecha fija. Con la mejora iterativa y la conectividad, hoy se publican actualizaciones con mucha más frecuencia.
- **Compilación (build):** conjunto de cambios listos para el usuario.
- **Entrega continua:** el código siempre es publicable; se entrega por partes a QA, las compilaciones van a un entorno de pruebas, las pruebas automáticas buscan fallos y, tras aprobarse, pasan a producción (el sitio activo). Acelera el desarrollo porque se prueba una parte mientras se escribe otra.
- **Despliegue continuo:** si las actualizaciones pasan las pruebas predefinidas, se envían directamente al sitio activo sin intervención manual; elimina el retraso entre el cambio y su visibilidad.

**DevOps.** Rol y método que reúne a negocio, desarrollo y operaciones de TI, antes aislados en silos. Beneficios citados: responder más rápido a los usuarios, desplegar de forma continua en desarrollo, pruebas y producción, escalar sin interrumpir el negocio, mantener coherencia entre pruebas y producción, más calidad y estabilidad, y menores costes.

**Ciclo de vida de DevOps** (repetible, seis flujos de trabajo):
1. **Planificación:** decidir funciones para la próxima versión según comentarios y uso; se crea un **backlog** priorizado.
2. **Desarrollo:** programar y probar lo del backlog, normalmente en el equipo local.
3. **Integración:** fusionar el código nuevo con el existente, extraerlo del repositorio, probarlo y prepararlo.
4. **Despliegue:** subir a transferencia, probar calidad y conformidad legal; a veces se lanza primero a un grupo pequeño y luego a todos.
5. **Operaciones:** vigilar rendimiento y **disponibilidad**, y avisar si algo falla (red, almacenamiento, servidor, seguridad).
6. **Aprendizaje:** recoger comentarios de usuarios, que alimentan la siguiente planificación.

Durante todo el ciclo se prueba, se cumple la seguridad y se cuida la conformidad. Los equipos pueden añadir o quitar flujos.

**Shift left (desplazamiento a la izquierda).** Llevar antes y con más frecuencia ciertas actividades en el flujo de trabajo. El material cita como ejemplo un sitio gubernamental de seguros de salud de EE. UU. lanzado en 2013, cuyos problemas iniciales se atribuyeron a la comunicación entre equipos y a pruebas insuficientes de back-end y front-end. Áreas desplazadas:
- **Pruebas continuas:** pruebas de unidad mientras se escribe, revisión de un homólogo e integración, repetidas en cada despliegue.
- **Seguridad:** desde el principio, cuando resolver problemas es más barato, y revisada de forma continua.
- **Conformidad con la normativa:** cumplimiento de leyes (sectores muy regulados como salud y finanzas) desde etapas tempranas.

### Módulo 4: Entrega de sitios web a todos los dispositivos
**Entrega como sitio web (HTTP).** El explorador y el servidor se comunican por HTTP en tres etapas:
1. El explorador envía una solicitud con una URL (recurso: contenido web, datos de una base de datos o herramienta back-end) y un método (acción: obtener un archivo, añadir o borrar datos).
2. Se inicia una **sesión**: el servidor crea un ID de sesión y lo envía en la respuesta; el explorador lo incluye en cada solicitud posterior para que el servidor recuerde las acciones y datos.
3. El servidor procesa la solicitud y devuelve una respuesta. Si es HTML, el explorador lo representa; si referencia CSS, JavaScript o imágenes, pide esos archivos con nuevas solicitudes.

Las sesiones son necesarias porque HTTP es **sin estado**: cada solicitud es independiente y el servidor no recuerda las anteriores. El ID de sesión cumple un papel como el número de pedido en la analogía de la pizzería. La duración de las sesiones la fijan los desarrolladores.

**Diseño reactivo.** Adapta el aspecto del sitio al factor de forma (de móviles pequeños a monitores grandes), con tecnologías como CSS. Antes se hacían a veces dos versiones (escritorio y móvil); hoy se crea el sitio una sola vez. No cambia cómo se entrega el sitio, sino cómo se desarrolla. Consideraciones:
- **Contenido:** lo que funciona en un portátil puede no funcionar en un móvil (por ejemplo, un diagrama detallado se adapta o se sustituye por una descripción).
- **Experiencia:** desplazamiento vertical, uso solo táctil frente a teclado y ratón, imágenes y vídeos que se adapten, fuentes legibles, menús adaptables.
- **Pruebas:** continuas desde el inicio. Las herramientas de desarrollador del explorador permiten **emular** tabletas y móviles desde un ordenador.
- **Marcos (frameworks):** paquetes de código reutilizables. **Bootstrap** (código abierto, CSS y JavaScript, creado originalmente por Twitter) aporta clases como `container-fluid`, que ajusta el elemento al tamaño de pantalla. Al desplegar, los archivos del marco viajan con el sitio. En los puntos finales del material se añade que los marcos también ofrecen bibliotecas para gestión de datos, control de la interfaz y tareas comunes como formularios.

**Entrega como aplicación web.** Una aplicación web se entrega totalmente en línea y se ejecuta en el explorador; puede ser tan potente como una de escritorio (hojas de cálculo, diagramas, juegos con gráficos). Ejemplos citados: Miro y Lucidchart. Muchas pueden instalarse en el dispositivo, y entonces son un **híbrido** entre app de tienda y página web. Se empaquetan con un **wrapper de aplicaciones** (contenedor de software en el que se coloca el sitio; analogía de la empanada).

Frente a las **aplicaciones nativas** (programadas con lenguajes que interactúan directamente con el sistema operativo), los wrappers ofrecen interfaces al sistema operativo: acceso al sistema de archivos (por ejemplo, guardar fotos), cambio de ajustes (ubicación) y notificaciones, y permiten acceder a parte del contenido sin conexión. Consideraciones:
- **Datos:** empaquetar textos e imágenes de la interfaz y decidir qué hacer sin datos (por ejemplo, mostrar los últimos datos vistos y actualizarlos al reconectar).
- **Plataforma:** Android, iOS e iPadOS admiten apps web, pero los wrappers difieren (por ejemplo, en el acceso a archivos); hay que adaptar funciones y pruebas.
- **Soporte y mantenimiento:** un solo sitio es más fácil de mantener; conviene minimizar personalizaciones por plataforma para no multiplicar los sitios a mantener.

### Módulo 5: Servicios y herramientas para pruebas y despliegue
**Virtualización.**
- **Contenedor:** paquete pequeño con solo las partes del sistema operativo que necesita un código concreto; usa menos memoria, disco y potencia.
- **Máquina virtual (VM):** software que imita un sistema completo (hardware y sistema operativo como Linux o Windows); consume más recursos. Pueden coexistir varias VM en un mismo hardware. Para tareas pequeñas, un contenedor es más eficiente.
- **Usos en pruebas:** ejecutar el sitio con datos sensibles reales en una VM con seguridad añadida; colocar la aplicación en un **recinto de pruebas** (sandbox) que la aísla pero imita un entorno real (por ejemplo, exponerla a un virus sin infectar la red); probar con distintos exploradores y entornos sin comprar hardware.
- **Pruebas de máquina limpia:** una máquina con solo el sistema operativo permite probar con menos variables. Es difícil en hardware físico, pero fácil en VM con una **unidad básica** (sistema operativo) y una **unidad de diferenciación** (cambios como instalar un explorador); para volver a limpio se borra la unidad de diferenciación y se crea otra desde la básica.

**Herramientas de tiempo de ejecución** (el sitio corre en un servidor, no necesariamente público ni activo):
- **Herramientas para desarrolladores del explorador:** gratuitas; permiten ver el código fuente, depurar y modificar el HTML en ejecución. En Chrome y Edge (basados en Chromium) se llaman "Herramientas para desarrolladores"; en Safari se activa el menú Desarrollo; en Firefox, "Herramientas del desarrollador web".
- **Herramientas de pruebas de API:** las API exponen métodos; el más habitual para enviar datos es POST y para recuperarlos, GET. **Postman** (con opción gratuita) permite crear solicitudes GET y POST y ver cómo responde la API.
- **Herramientas de pruebas de rendimiento:** devuelven métricas. Ejemplo: **tiempo hasta el primer byte** (retardo entre pedir la página y recibir los primeros datos). **Lighthouse** (integrado en Chrome) mide First Contentful Paint (primer contenido pintado), Índice de velocidad (rapidez con que se muestra el contenido), Time to Interactive (cuándo la página es totalmente interactiva) y Total Blocking Time (tiempo bloqueado sin responder a la entrada del usuario). **GTmetrix** no depende del explorador: se escribe una URL y genera un informe, a veces con recomendaciones.

**Herramientas y servicios de despliegue.** Tres modalidades: **local** (servidores propios), **en la nube** (por ejemplo, IBM Cloud o Amazon Web Services) e **híbrido** (parte local, parte en nube, por ejemplo datos en servidores propios y contenido desde la nube). El despliegue en la nube se está convirtiendo en el estándar.
- **CLI (interfaz de línea de comandos):** entrada y salida solo de texto; permite ejecutar archivos de texto con comandos (archivos de proceso por lotes) y así automatizar pasos del despliegue. Ejemplo mencionado: PowerShell de Microsoft.
- **Integración del código:** la **integración continua** reúne periódicamente el código de varios desarrolladores para probarlo y desplegarlo. GitHub la incluye como característica central; IBM UrbanCode también y admite automatizar herramientas como Jenkins.
- **Herramientas de planeación:** permiten programar sucesos con fecha y hora. Ejemplo del material: código listo a las 12:30, integración automática a las 17:00, pruebas automáticas y, si pasan, despliegue a un servidor de transferencia.
- **Planos (blueprints):** modelo visual de los pasos del despliegue (recursos, software y procesos automáticos) que permite ajustar cada etapa. UrbanCode tiene plano gráfico; GitHub ofrece el visualizador de flujos de trabajo.
- **Herramientas basadas en la nube:** los proveedores incluyen las herramientas de despliegue y admiten integraciones (GitHub y Jenkins funcionan con los principales proveedores). UrbanCode ofrece un panel que muestra el estado de cada paso para investigar fallos.

### Módulo 6: Despliegue en la nube
**Qué es la nube.** Término que se refiere en general a Internet; en entornos técnicos, el conjunto de servicios y almacenamiento de los que dependen empresas y usuarios. Aporta copia de seguridad y recuperación ante fallos de sistemas locales. Su origen documentado es un dibujo de ingeniería donde una nube representaba la red.

**Evolución del hardware.** Primero, servidores web potentes (incluso uno bajo un escritorio en una pyme); después, **granjas de servidores** que reparten cargas de trabajo; la nube separa las funciones (almacenamiento, procesamiento, red, software especializado) en servidores dedicados para que los desarrolladores usen solo lo que necesitan. Según el material, los servicios seguirán especializándose, siendo más rápidos y de menor consumo.

**Servicios de la nube para desarrolladores web.**
- **Alojamiento:** plantillas para sistemas de gestión de contenidos (WordPress, Drupal), y alojamiento y gestión de nombres de dominio.
- **Réplica:** copia automática del código del sitio en servidores de todo el mundo para reducir la **latencia**.
- **Escalabilidad:** se paga solo por la capacidad usada y se puede volver atrás.
- **Seguridad:** herramientas contra amenazas como los ataques de **denegación de servicio (DoS)**, que saturan el servidor con solicitudes falsas; la nube puede bloquearlas o alertar.
- **Supervisión:** estado de los servicios, tráfico y solicitudes, con paneles personalizables, para escalar hacia arriba o abajo.
- **Herramientas de desarrollo:** soluciones back-end (como IBM Vapor), editores de código (como Visual Studio Code), CLI, creación de páginas y conectores, y recursos para crear servidores web, VM, contenedores y **funciones** (software para tareas muy específicas del sitio).

**Contenedores.** Un contenedor de software es un paquete estandarizado (como un contenedor de transporte) con código, entorno de ejecución, bibliotecas, herramientas del sistema y configuración. Se desarrolló para evitar instalar un sistema operativo completo (físico o en VM) cuando solo se necesita una parte. Ventajas:
1. El código deja de depender del hardware: entornos autónomos y portátiles desplegables en distintos sistemas.
2. Un contenedor puede ejecutar desde un sitio estático hasta una aplicación grande; las organizaciones dividen sitios grandes en **microservicios** (autenticación, recomendaciones, menús, búsqueda) empaquetados en contenedores. Ejemplo citado: la selección de vídeo de una plataforma de streaming como microservicio.

Los contenedores sirven para alojar web, bases de datos, audio y vídeo, y para proporcionar datos al front-end.

## Código y ejemplos

**Clase de Bootstrap para un contenedor adaptable.** Un `div` con `container-fluid` ocupa el ancho disponible y se ajusta a la pantalla sin escribir CSS propio. Resultado: el bloque se estira o se reduce según el dispositivo.

```html
<!-- El marco Bootstrap debe estar incluido en la página -->
<div class="container-fluid">
  <h1>Catálogo de plantas</h1>
  <p>Este bloque se adapta al ancho de la pantalla.</p>
</div>
```

**Ciclo básico de control de versiones desde la terminal.** Ilustra los pasos descritos (clonar, captar, confirmar, enviar). Los nombres de repositorio y rama son inventados; el material describe los pasos pero no muestra comandos. La solicitud de extracción se hace en la plataforma del repositorio, no en estos comandos.

```bash
# 1. Clonar el repositorio remoto en la máquina local
git clone https://example.com/equipo/tienda-web.git
cd tienda-web

# 2. Captar los últimos cambios del repositorio remoto
git fetch origin

# 3. Confirmar los cambios con un mensaje breve
git add .
git commit -m "Corrige el enlace roto del pie de página"

# 4. Enviar la copia local al repositorio remoto
git push origin main
```

**Archivo de proceso por lotes sencillo.** Un archivo de texto con comandos que la línea de comandos ejecuta de una vez; es la base para automatizar pasos de un despliegue. Resultado: lista los archivos de la carpeta y muestra un mensaje.

```bash
#!/bin/bash
# Lista el contenido de la carpeta actual y muestra un aviso final
ls
echo "Revision de archivos terminada"
```

## Errores comunes
- Dejar las pruebas para el final del desarrollo: el diseño reactivo, la seguridad y la conformidad deben considerarse desde el principio.
- Probar solo en un tipo de dispositivo y asumir que el contenido funciona igual en móvil.
- Colocar el servidor web y la base de datos en regiones distintas de la nube, lo que ralentiza las respuestas.
- Exponer datos sensibles (como contraseñas) en el código o descuidar la seguridad de las API.
- Mantener funciones, pruebas y operaciones aisladas, sin comunicación entre equipos.
- Añadir muchas personalizaciones por plataforma en una app web, lo que multiplica los sitios que mantener.

## Herramientas
- **IBM UrbanCode:** despliegue con integración continua, planos gráficos y panel de estado.
- **Jenkins:** automatización de código abierto para integración y pruebas.
- **GitHub:** repositorio con herramientas de despliegue, integración de código y visualizador de flujos de trabajo.
- **Postman:** pruebas de llamadas API con métodos GET y POST.
- **Lighthouse (Google) y GTmetrix:** medición de rendimiento.
- **Herramientas para desarrolladores del explorador:** depuración, edición del HTML en vivo y emulación de dispositivos.
- **Bootstrap:** marco para diseño reactivo.
- **PowerShell:** ejemplo de línea de comandos.
- **Visual Studio Code, IBM Vapor:** editor de código y herramienta de back-end citados entre las herramientas de desarrollo en la nube.
- **IBM Cloud, Amazon Web Services:** proveedores de nube mencionados.

## Preguntas de repaso

1. ¿Qué diferencia hay entre una prueba de rendimiento y una prueba de estrés?
   **Respuesta:** Ambas miden el comportamiento bajo carga, pero la de rendimiento evalúa distintos niveles de estrés (la de carga, condiciones reales), mientras que la de estrés usa cargas extremas para saber cuánto aguanta el sitio antes de fallar.

2. Indica en orden los pasos típicos de un flujo de control de versiones.
   **Respuesta:** Clonar el repositorio, captar los cambios más recientes, hacer commit de los cambios con un mensaje, abrir una solicitud de extracción para que el equipo la revise y fusione, y hacer push al repositorio remoto.

3. ¿En qué se diferencian la entrega continua y el despliegue continuo?
   **Respuesta:** La entrega continua envía las compilaciones a un entorno de pruebas donde se verifican automáticamente y requiere aprobación para pasar a producción. El despliegue continuo publica automáticamente en el sitio activo los cambios que superan las pruebas, sin intervención manual.

4. ¿Por qué se necesitan las sesiones y el ID de sesión en la web?
   **Respuesta:** Porque HTTP es sin estado y el servidor no recuerda solicitudes anteriores. El ID de sesión, enviado en cada solicitud, permite al servidor y al explorador recordar quién es el usuario y qué datos e interacciones ha habido en esa sesión.

5. ¿Qué ventajas aporta un contenedor frente a una máquina virtual?
   **Respuesta:** Un contenedor incluye solo las partes del sistema operativo necesarias, así que usa menos memoria, disco y potencia que una VM, que imita un sistema completo con su sistema operativo. Además es autónomo y portátil, independiente del hardware, y permite empaquetar microservicios.
