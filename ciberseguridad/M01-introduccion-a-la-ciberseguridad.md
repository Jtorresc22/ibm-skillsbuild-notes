# Cybersecurity Fundamentals - M01: Introducción a la ciberseguridad

## Resumen

La ciberseguridad es la práctica de proteger y recuperar datos, redes, dispositivos y programas frente a amenazas de origen digital, humano o físico. Sus objetivos se resumen en la tríada CID (confidencialidad, integridad, disponibilidad), que se logran con controles. Una organización se apoya en tres elementos (formación, proceso, tecnología) y decide sobre el riesgo según su valor y su tolerancia. El módulo cierra con mitos sobre la profesión y con un repaso de leyes y debates éticos.

Nota de estructura: el material agrupa cinco secciones internas (originalmente rotuladas "Módulo 1" a "Módulo 5") dentro de este único módulo.

## Conceptos clave

- **Ciberseguridad:** proteger y recuperar datos, redes, dispositivos y programas frente a amenazas.
- **Componentes:** digital, humano y físico; una buena estrategia cubre los tres.
- **Tríada CID:** confidencialidad, integridad y disponibilidad.
- **Control:** medida o contramedida para evitar, detectar, contrarrestar o minimizar riesgos de seguridad.
- **Formación, proceso, tecnología:** los tres elementos sobre los que se centran los esfuerzos de una organización.
- **Riesgo:** posibilidad de que ocurra algo con consecuencia negativa.
- **Valor del riesgo:** consecuencia x probabilidad.
- **Respuestas al riesgo:** aceptación, reducción, transferencia, rechazo.
- **Tolerancia al riesgo:** nivel de riesgo que la organización está dispuesta a asumir.
- **Adversario:** entidad que quiere comprometer un sistema de información.

## Detalle por tema

### 1. Qué es la ciberseguridad

- La tecnología digital e Internet (incluido el IoT) generan gran cantidad de datos y aumentan la huella digital de las personas, que resulta vulnerable si no se protege.
- Definir la ciberseguridad solo como seguridad de sistemas o de comunicaciones es incompleto. Dos ejemplos del material: un estafador que pide el PIN por correo haciéndose pasar por un banco, y un investigador privado que convence a un empleado de dejar documentos impresos para recogerlos. Ambos muestran que hay componentes no digitales.
- **Seguridad digital:** protege datos y sistemas frente a malware (virus, ransomware) y hackeo. Medidas: cortafuegos, cifrado.
- **Seguridad humana:** protege frente a amenazas derivadas de acciones de personas, involuntarias (abrir un adjunto malicioso) o intencionadas (filtrar datos). Medidas: formación de empleados, políticas de contraseñas fuertes.
- **Seguridad física:** protege activos tangibles que sostienen la infraestructura (estaciones de trabajo, salas de servidores, centros de datos) frente a robo, manipulación o desastres naturales. Medidas: vigilancia, control de acceso, planes de recuperación ante desastres.

### 2. La tríada CID

- **Confidencialidad:** solo las personas autorizadas acceden a los datos o los divulgan. Ejemplos: código fuente restringido a quienes lo necesitan; datos clínicos accesibles solo para el paciente y el personal sanitario autorizado. En la práctica: nivel de acceso adecuado, al usuario adecuado, en el momento y con los métodos adecuados.
- **Integridad:** los datos son fiables y exactos, sin modificación ni destrucción no autorizada. Ejemplo: una compra de 10 EUR que acaba registrada como 10 000 EUR, por fallo técnico o error humano. Se solapa con la confidencialidad porque también exige impedir cambios a personas no autorizadas.
- **Disponibilidad:** acceso y uso oportunos y fiables. Ejemplo: banca en línea 24/7. "Oportuno" no siempre es inmediato (los expedientes escolares pueden tardar días), pero debe ser en un plazo razonable.
- Cada organización puede priorizar un objetivo según su actividad:
  - Servicios de inteligencia gubernamentales: confidencialidad.
  - Bancos: integridad de las transacciones.
  - Minorista online: disponibilidad (el tiempo de inactividad hace perder ventas y reputación).

### 3. Controles por objetivo

- **Confidencialidad:** cifrado, controles de acceso (contraseñas, biometría como huellas o retina), gestión de parches.
- **Integridad:** sumas de verificación, controles de acceso y permisos de usuario, copias de seguridad, registros de auditoría.
- **Disponibilidad:** sistemas redundantes y copias de seguridad, antimalware y cortafuegos, planes de recuperación ante desastres y de continuidad del negocio.

### 4. Elementos clave: formación, proceso y tecnología

- **Formación:** sesiones periódicas y cultura de concienciación reducen conductas de riesgo y aumentan los reportes de actividad sospechosa; funcionan como "cortafuegos humano".
- **Proceso:** puede ayudar o estorbar. Un reporte de incidentes con una encuesta de 20 preguntas desalienta a la gente. Un buen proceso es claro y simple, accesible/conocido (como las rutas de evacuación señalizadas) y coherente (sin excepciones que aumenten la complejidad y que un atacante pueda explotar).
- **Tecnología:** infraestructura subyacente (cifrado de dispositivos, protección perimetral, antimalware). Debe resolver problemas sin crear otros: si es poco intrusiva, protege de forma pasiva; si se implanta mal, los usuarios intentan desactivarla.

### 5. Gestión de riesgos

- **Valor del riesgo = consecuencia x probabilidad.** Consecuencia: impacto y daño. Probabilidad: frecuencia con la que ocurre el impacto. Los riesgos de mayor valor son "riesgos altos" y requieren mitigación inmediata.
- Ejemplo de riesgo bajo: pinchazo de un coche (1 de cada 10 al año) que cuesta una jornada de trabajo.
- En ciberseguridad la probabilidad es difícil de medir directamente. Se estima como: **probabilidad = capacidad del adversario x motivación del adversario x gravedad de la vulnerabilidad.**
  - Capacidad: recursos, acceso a tecnología y experiencia.
  - Motivación: ganancia financiera, información, influencia política o simple emoción.
  - Vulnerabilidad: debilidad explotable (por ejemplo, un inicio de sesión que no autentica bien).
- Ejemplo del material: un grupo nuevo de hackers contra un banco. Capacidad baja, motivación alta, vulnerabilidad alta (fácil de explotar, descrita públicamente).
- Calificar en bajo/medio/alto es un análisis **cualitativo**; lo ideal serían números o porcentajes, pero a menudo solo hay estimaciones.
- **Respuestas ante el riesgo** (con el ejemplo de la pastelería casera y el riesgo de incendio):

| Respuesta | Qué implica | Ejemplo |
|---|---|---|
| Aceptación | Se asume el riesgo; lo decide un propietario de riesgos (alto rango) | Confiar en que es improbable y reparar la cocina si ocurre |
| Reducción | Bajar probabilidad o consecuencia con controles o parches | Detector de humo o sistema de extinción |
| Transferencia | Un tercero asume parte o todo el riesgo (seguro, subcontratación) | Ampliar el seguro para cubrir incendios |
| Rechazo | Se desiste de la actividad que genera el riesgo | Hacer repostería sin horno o no abrir el negocio |

- **Tolerancia al riesgo:** alta = acepta riesgos y adopta tecnologías nuevas, con buenas contingencias; baja = prioriza estabilidad (cortafuegos, cifrado, actualizaciones) aunque pierda oportunidades. Ninguna es mejor; debe alinearse con objetivos y recursos.

### 6. Conceptos erróneos sobre la profesión

- No todo el mundo viene de TI: se necesitan habilidades de gestión de personas, comunicación, matemáticas, ciencia de datos.
- No todos los hackers son criminales: el término originalmente designa a quien disfruta adaptando cosas y entendiendo cómo funcionan; hoy muchos trabajan en funciones legítimas de TI.
- Hay sitio para perfiles diversos, desde análisis estratégico hasta vigilancia y paciencia en monitorización de sistemas.
- La edad no es barrera: los equipos se benefician de perspectivas nuevas y experimentadas.

### 7. Leyes

- La ciberdelincuencia es un concepto reciente (unos 30 años); antes se usaban leyes de robo y telegrafía, poco aplicables. Las leyes varían por país: hay que conocer las del lugar donde se vive o al que se viaja.
- **Uso indebido de ordenadores:**
  - Uso o control no aprobado de un dispositivo, incluida la elusión de autenticación (ejemplo: pantalla de login falsa para robar contraseñas).
  - Impedir el uso legítimo de otros, es decir, ataques a la disponibilidad (ejemplo: saturar un servidor o switch con paquetes).
  - Ayudar a otros delincuentes o crear malware (ejemplo: programa de acceso remoto encubierto).
- **Otras leyes:**
  - Alteración no autorizada de datos (ejemplo: cambiar saldos en la base de datos de un banco).
  - Software prohibido: crear, usar o distribuir malware o herramientas de hackeo (ejemplo: PDF con virus enviado por correo).
  - Acoso cibernético: conductas dañinas o amenazantes en línea; se aplica cuando la víctima se siente insegura o asustada.
- Algunos delitos se solapan con leyes de protección de datos o de propiedad (el robo de propiedad intelectual puede tratarse como robo).
- Regla de oro antes de experimentar con un dispositivo: obtener permiso del propietario y saber exactamente lo que se hace para evitar efectos secundarios.

### 8. Ética

- Las posturas éticas varían igual que las leyes. Ejemplo: dejar archivos-trampa ocultos en la infraestructura; muchos lo ven como ético, pero en la mayoría de legislaciones es ilegal por considerarse malware.
- **Represalias:** contraataque o defensa activa (rastrear y perturbar a los atacantes). Se defiende como protección y disuasión; se critica por riesgo de escalada.
- **Inteligencia artificial:** dudas sobre responsabilidad ante errores, transparencia, grado de confianza y uso indebido.
- **Uso gubernamental:** unidades de guerra cibernética (protección de infraestructura crítica, vigilancia, ciberataques) con regulación variable y ambigua; no hay consenso sobre aplicar las leyes de guerra tradicionales. La vigilancia estatal exige equilibrar seguridad nacional y privacidad.

## Amenaza - Control

| Amenaza | Objetivo afectado | Control mencionado |
|---|---|---|
| Acceso a datos por personas no autorizadas | Confidencialidad | Cifrado, controles de acceso, biometría |
| Software desactualizado con debilidades explotables | Confidencialidad | Gestión de parches |
| Modificación no autorizada o accidental de datos | Integridad | Sumas de verificación, permisos de usuario, copias de seguridad, registros de auditoría |
| Fallos de sistema, pérdida de datos, interrupción de servicio | Disponibilidad | Sistemas redundantes, copias de seguridad, planes de recuperación y continuidad |
| Malware (virus, ransomware) y ataques que interrumpen servicios | Disponibilidad / digital | Antimalware, cortafuegos |
| Error o mala intención de empleados | Humano | Formación y concienciación, políticas de contraseñas fuertes |
| Robo, manipulación o desastres naturales | Físico | Vigilancia, control de acceso, planes de recuperación ante desastres |
| Procesos confusos o incoherentes que frenan los reportes | Proceso | Procesos claros, accesibles y coherentes |
| Tecnología intrusiva que los usuarios desactivan | Tecnología | Implantación poco intrusiva (por ejemplo, gestión de dispositivos) |
| Estafa por correo o llamada para obtener datos o documentos | Humano | No cubierto como control específico (el material solo lo usa como ejemplo de componente no digital) |

## Herramientas

- **Herramientas y tecnologías citadas** (a nivel conceptual, sin comandos): cifrado, cortafuegos, antimalware, sumas de verificación, registros de auditoría, copias de seguridad, sistemas redundantes, software de gestión de dispositivos (seguimiento y aplicación de parches).


## Preguntas de repaso (5) y sus respectivas respuestas

1. **¿Cuáles son los tres componentes que puede tener la ciberseguridad y un ejemplo de medida de cada uno?**
   Digital (cortafuegos o cifrado), humano (formación de empleados o políticas de contraseñas) y físico (vigilancia, control de acceso, recuperación ante desastres).

2. **¿Qué objetivo de la tríada CID suele ser el más crítico para un banco y por qué?**
   La integridad, porque las transacciones dependen de datos exactos y coherentes; una modificación no autorizada, deliberada o no, puede causar pérdidas y consecuencias legales.

3. **¿Cómo se calcula el valor de un riesgo y cómo se estima la probabilidad en ciberseguridad?**
   Valor = consecuencia x probabilidad. La probabilidad se estima como capacidad del adversario x motivación del adversario x gravedad de la vulnerabilidad.

4. **¿Cuáles son las cuatro respuestas ante un riesgo y en qué se diferencia la transferencia del rechazo?**
   Aceptación, reducción, transferencia y rechazo. En la transferencia un tercero (seguro o subcontratista) asume parte o todo el riesgo y la actividad continúa; en el rechazo la organización abandona la actividad que genera el riesgo.

5. **¿Qué tres atributos debe tener un buen proceso de seguridad?**
   Ser claro y lo más simple posible, ser accesible o bien conocido, y ser coherente (sin contradicciones ni excesivas excepciones).
