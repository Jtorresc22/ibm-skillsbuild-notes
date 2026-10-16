# Desarrollar una página web de lista de tareas interactiva - M06

## Resumen
Proyecto guiado en el que se asume el rol de desarrollador web front-end junior en una empresa de artículos para el hogar. El objetivo es construir una lista de tareas interactiva para uso interno de los empleados. Se combinan HTML, CSS y JavaScript, y se trabaja en un IDE (la versión en línea de Visual Studio Code). El material cubre además qué probar (aspectos visuales y funcionalidad) y cómo documentar el proyecto.

## Conceptos clave
- **IDE:** entorno donde se escribe y prueba el código, con ayudas de sintaxis y comentarios visuales.
- **Elemento hijo:** elemento cuyas etiquetas de apertura y cierre quedan dentro de las de otro.
- **Atributo id vs. class:** el id identifica un elemento concreto como selector de estilo; la clase puede aplicarse a uno o varios.
- **Selector de ID, de clase y encadenado:** formas de apuntar estilos CSS a elementos.
- **Pseudoelemento:** permite dar estilo a una parte de un elemento.
- **Escucha de sucesos y manejador de sucesos:** el primero detecta la interacción; el segundo es la función que se ejecuta como respuesta.
- **querySelector:** método de JavaScript para localizar elementos HTML y modificarlos.
- **Plan de pruebas:** revisión de aspectos visuales y de funcionalidad antes de dar la página por buena.
- **Documentación del proyecto:** registro de lo hecho y aprendido, sin datos personales.

## Detalle por tema

### Rol y contexto (Módulo 1: "Es un desarrollador web")
- Puesto de front-end de nivel básico; el equipo crea sitios web internos que ayudan a otros empleados a ser más productivos.
- Kit de herramientas: IDE, máquinas virtuales para probar en distintos escenarios, editores gráficos para imágenes y vídeo, y acceso a Internet para investigar, consultar sintaxis y colaborar.
- Conocimientos aplicables: HTML para estructura, CSS para estilos, JavaScript para interactividad, lectura de código ajeno, atributos HTML, estructura básica, modelo de cuadro CSS para el diseño, diseño reactivo, depuración, pruebas (incluidas VM y distintas orientaciones de la UI).
- En este proyecto se practica solo una parte de esos conocimientos, con simulaciones.

### Conceptos HTML
- Un elemento puede ser hijo de otro.
- `id` sirve para un elemento; `class` para uno o varios.
- El elemento de cabecera (head) es donde se referencian archivos externos, como scripts o CSS.

### Estilos con CSS
- Selector de ID: almohadilla (`#tasks`).
- Selector de clase: punto (`.tasks`).
- Selector encadenado: nombres unidos con punto (`.tasks.overflow`), para agrupar por características comunes como tipo de elemento o nombre de clase.
- Pseudoelemento: dos signos de dos puntos (`tasks::-webkit-scrollbar`), para estilizar una parte del elemento.

### Interactividad con JavaScript
- Un escucha de sucesos (por ejemplo, onclick) espera la acción del usuario y lanza un manejador en forma de función.
- Puede reaccionar a teclado y ratón.
- Puede cambiar otras partes de la UI; ejemplo del material: tachar el texto de una tarea al marcar su casilla de completada.

### Diseño de página con JavaScript
- Puede crear elementos HTML y colocarlos dentro de otros existentes.
- Con querySelector encuentra elementos y los modifica.
- Puede mostrar u ocultar elementos según escenarios definidos; ejemplo: mostrar una barra de desplazamiento al superar cierta altura y ocultarla por debajo.
- El material incluye una tabla de sintaxis JavaScript como imagen; su contenido no está disponible en el texto (no cubierto).

### Pruebas rápidas
Lista de comprobación del material:
- **Aspectos visuales**
  - Colores: ¿cumplen requisitos y wireframes?, ¿valores hexadecimales correctos en el CSS?
  - Diseño: elementos solapados, espaciado adecuado, elementos que desaparecen al añadir tareas, barras de desplazamiento coherentes con el diseño, CSS acorde a requisitos y wireframes.
  - Información al usuario: mensajes que aparecen como se espera, claros y legibles, indicaciones sobre qué hacer, etiquetas de botón claras.
- **Funcionalidad**
  - Botones, interacciones de teclado y casilla que cambia el aspecto de la tarea.
  - Barras de desplazamiento, elementos generados por JavaScript y mensajes al usuario.

### Documentar el proyecto
Conviene registrar:
- Utilidad de los requisitos y del wireframe para guiar el desarrollo.
- Zonas del código que se quieren seguir estudiando.
- Funciones útiles que quedaron fuera del alcance.
- Comentarios recibidos de los usuarios.
- Errores encontrados y cómo se resolvieron.
- Ayudas de codificación encontradas o creadas.
- Dificultades y logros.

No deben incluirse nombres ni datos personales. Con el tiempo, esto forma un catálogo de consulta para páginas similares.

### Conclusiones
- Es importante entender cómo los tres lenguajes funcionan juntos; se puede alternar entre HTML y CSS hasta encontrar el método propio.
- Las pruebas deben asegurar que la página no tiene errores. Para una página pública podría probarse el comportamiento a gran escala (por ejemplo, cientos de usuarios simultáneos).
- Sugerencia del material: el voluntariado para organizaciones sin ánimo de lucro como práctica.

## Herramientas
- Visual Studio Code (versión en línea), usado como IDE.
- Máquinas virtuales para probar escenarios.
- Editores gráficos para imágenes y vídeo.
- Acceso a Internet para consulta y colaboración.

## Laboratorio
- **Contexto:** se partió de los requisitos del gestor de producto y de un wireframe del diseñador web.
- **Simulaciones realizadas:**
  1. Usar VS Code como IDE: instalar una extensión y preparar archivos HTML, CSS y JavaScript vacíos.
  2. Escribir HTML con la estructura y los elementos de la página.
  3. Dar estilo con CSS.
  4. Añadir interactividad y diseño con JavaScript.
  5. Probar la página.
- **Resultado:** una lista de tareas interactiva para que los empleados sigan sus tareas de trabajo.
- El código concreto de las simulaciones no se incluye en el material (no cubierto).

## Preguntas de repaso

1. ¿Qué diferencia hay entre un atributo `id` y un atributo `class` como selectores de estilo?
   **Respuesta:** el `id` se usa sobre un elemento concreto, mientras que la clase puede aplicarse a uno o más elementos.

2. ¿Cómo se escriben los selectores de ID, de clase y los pseudoelementos en CSS?
   **Respuesta:** el de ID con almohadilla (`#tasks`), el de clase con punto (`.tasks`) y el pseudoelemento con dos signos de dos puntos (`tasks::-webkit-scrollbar`).

3. ¿Qué papel cumplen el escucha de sucesos y el manejador de sucesos?
   **Respuesta:** el escucha detecta la interacción del usuario con un elemento (por ejemplo, onclick) y el manejador es la función que se ejecuta como respuesta.

4. Menciona dos comprobaciones de aspectos visuales y dos de funcionalidad que propone el material.
   **Respuesta:** visuales: elementos solapados, colores hexadecimales correctos o mensajes claros; funcionalidad: botones que funcionan como se espera, interacciones de teclado o la casilla que cambia el aspecto de la tarea (cualquier dos de cada tipo).

5. ¿Qué información debe documentarse al terminar el proyecto y qué no debe incluirse?
   **Respuesta:** utilidad de requisitos y wireframe, código a revisar, funciones fuera de alcance, comentarios de usuarios, errores y soluciones, ayudas de codificación, dificultades y logros; no deben incluirse nombres ni datos personales.
