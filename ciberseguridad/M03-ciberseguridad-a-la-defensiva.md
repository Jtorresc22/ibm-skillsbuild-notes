# Cybersecurity Fundamentals - M03: Ciberseguridad a la defensiva

## Resumen

El módulo plantea la defensa como un ciclo de cuatro momentos: prevenir, detectar, responder y aprender, enmarcados en una estrategia de seguridad. Parte del impacto económico de las filtraciones de datos para justificar la inversión, y luego detalla estrategias de prevención (superficie de ataque, DMZ, mínimo privilegio, parches, defensa en profundidad), herramientas de detección (antimalware, registros, SIEM, SOC), el marco de respuesta a incidentes de SANS, los fundamentos de criptografía y la inteligencia de amenazas. La IA se presenta como apoyo en detección e inteligencia.

Nota de estructura: el material agrupa siete secciones internas (rotuladas "Módulo 1" a "Módulo 7") dentro de este único módulo.

## Conceptos clave

- **Estrategia de seguridad:** plan para proteger activos digitales y físicos; incluye evaluación de riesgos, políticas y procedimientos, concienciación y formación, respuesta a incidentes, y auditoría y pruebas.
- **Madurez de la seguridad:** capacidad real de proteger activos y responder a amenazas; se mide con modelos como C2M2.
- **Superficie de ataque:** todos los puntos por los que un atacante puede intentar entrar o dañar un sistema.
- **Mínimo privilegio y defensa en profundidad:** permisos mínimos necesarios y varias capas de controles.
- **SIEM y SOC:** herramienta que agrega y correlaciona datos de seguridad, y equipo que los vigila y responde.
- **Respuesta a incidentes (IR):** acciones para prepararse, detectar, detener y recuperarse de un ataque.
- **Criptografía:** principios y métodos para ocultar el contenido de los datos, evitar su uso no autorizado o impedir su modificación sin ser detectada (definición del NIST citada en el material).
- **Inteligencia de amenazas:** datos recopilados y analizados para entender motivos y comportamiento de los actores de amenazas.

## Detalle por tema

### 1. Impacto financiero

- **IBM/Ponemon, Cost of a Data Breach 2023:**
  - Coste medio total de una filtración: 4,45 M USD (15 % más que en 2020).
  - Coste medio por registro: 165 USD.
  - Tiempo medio de identificación y contención: 277 días.
  - El 57 % de las organizaciones subió precios tras una filtración.
  - Estados Unidos tuvo el coste más alto (9,48 M USD) y la sanidad fue el sector más caro (10,93 M USD).
  - Mayores contribuyentes al coste: detección y escalada (auditorías, análisis forense), y en segundo lugar la pérdida de negocio (daño de reputación que puede durar años).
  - Las multas administrativas pueden ser severas con el RGPD (datos de residentes de la UE).
- **Hiscox Cyber Readiness Report 2023** (más de 6000 profesionales):
  - El 53 % había sufrido un ciberataque (frente al 48 % del año previo).
  - Gasto medio en ciberseguridad: 155 000 USD (39 % más en tres años).
  - Coste medio de los ataques: bajó de unos 17 000 a 16 000 USD; uno de cada ocho ataques supera los 250 000 USD.
  - Pequeñas empresas (menos de diez empleados): gastan cuatro veces más que hace dos años, pero los ataques subieron del 23 al 36 % en tres años.
  - Una de cada tres sufrió fraude de desvío de pagos, la principal causa de pérdidas (engañar a una organización para que pague a una cuenta del atacante).
  - Una de cada cinco recibió una demanda de rescate; quienes pagaron bajaron del 66 al 63 %.
- Conclusión del material: los ciberataques son un coste inevitable; hay que aumentar la resiliencia y buscar asesoría profesional ante ransomware. Metáfora: un ciberataque es como un contaminante ambiental, ignorarlo agrava el problema.

### 2. Estrategia de seguridad

- Suele diseñarla un equipo de seguridad o un consultor; debe existir desde el inicio de la organización y revisarse al menos una vez al año.
- **Madurez (C2M2):** cuatro niveles (MIL0 a MIL3), de ninguna práctica a prácticas reactivas, proactivas y plenamente integradas (ver sección de frameworks). Una organización puede ser madura en un área y no en otra.
- Ejemplo del Departamento de Energía de EE. UU. aplicado a la reducción de vulnerabilidades: en MIL1 las acciones son ad hoc; en MIL2 hay monitorización de fuentes para activos prioritarios, evaluaciones periódicas, clasificación por gravedad, evaluación del impacto operativo antes de parchear y comunicación a interesados; en MIL3 la monitorización abarca todos los activos de TI y OT, evalúan personas independientes, se revisa la eficacia de las mitigaciones y se reciben informes externos de vulnerabilidades.
- **10 pasos del NCSC del Reino Unido:** gestión de riesgos; compromiso y formación; gestión de activos; arquitectura y configuración; gestión de vulnerabilidades; gestión de identidad y acceso; seguridad de datos; registro y supervisión; gestión de incidentes; seguridad de la cadena de suministro.
- Existe un mercado amplio de productos y servicios; las grandes organizaciones combinan proveedores (por ejemplo, DLP de uno y cortafuegos de otro).

### 3. Prevención de ataques

- No hay seguridad perfecta; el enfoque realista es encarecer el ataque hasta que no compense (si romper el sistema cuesta 100 000 USD al atacante y le reporta 80 000 USD, probablemente no lo intentará). Se logra con defensas superpuestas, parches regulares e inteligencia de amenazas. El objetivo es reducir el riesgo operativo a un nivel aceptable combinando formación, procesos y tecnología.
- **Reducir la superficie de ataque:** menos interfaces, protocolos y servicios expuestos. Ejemplo: limitar el acceso a un sistema de pagos a ubicaciones de oficina, de modo que el atacante deba comprometer primero un dispositivo de confianza. El acceso remoto y los dispositivos personales la amplían.
- **DMZ:** segmento de red entre la red interna e Internet, delimitado por cortafuegos externo e interno. Aloja servidores que deben ser accesibles desde fuera (web, correo, FTP, DNS) con datos públicos; un usuario externo llega a ellos pero no a registros de empleados ni datos financieros internos.
- **Mínimo privilegio:** conceder solo los permisos necesarios. Ejemplo: gerentes con acceso de solo lectura a los datos de sus equipos, de forma que si roban sus credenciales el daño se limita a la confidencialidad de esos registros. Reduce el "radio de explosión" y, con ello, el valor del riesgo.
- **Gestión de vulnerabilidades del software:**
  - Incluye la gestión de parches.
  - Cuando un proveedor deja de dar soporte (por ejemplo, Windows 7) no hay parches y esos equipos son blancos fáciles; se prefiere software con soporte o **controles compensatorios** (desactivar funciones, reforzar la red, vigilar más).
  - Las versiones nuevas pueden traer vulnerabilidades, así que conviene consultar a los proveedores; si no hay solución, se aplican controles temporales (desactivar una función o volver a una versión anterior).
  - Los escáneres de vulnerabilidades analizan sistemas en busca de software obsoleto, parches ausentes, configuraciones erróneas o contraseñas débiles; pueden basarse en la red (pruebas activas) o analizar código fuente estático.
- **Defensa en profundidad:** varias capas (red: cortafuegos; dispositivo: escáneres de malware; datos: cifrado); el atacante debe superarlas todas.

### 4. Detección de ataques

- **Antimalware (antivirus):** detecta, pone en cuarentena o elimina malware comparando archivos con **firmas** (patrones de malware conocido). Se instala en el dispositivo o se gestiona desde un servidor central.
- **Registro (logging):** grabar acciones de forma precisa en un lugar seguro, a prueba de manipulaciones, como historial permanente. Se registran inicios y cierres de sesión, intentos fallidos, cambios de configuración, tráfico de paquetes e inicio de procesos o servicios. Una entrada aislada vale poco, pero el conjunto sirve de pista de auditoría.
- **Monitorización de red (análisis de tráfico):** observa origen y destino, protocolos, ancho de banda y tamaño de paquetes; puede identificar actividad aun cifrada, aplicaciones, código malicioso y anomalías. Ejemplo: streaming = consumo alto y sostenido; descarga grande = pico puntual.
- **SIEM:** recopila y agrega datos de toda la infraestructura para identificar eventos y patrones de ataque. Ejemplo: alerta si hay cinco o más inicios de sesión fallidos por minuto en una cuenta (posible fuerza bruta).
- **SOC:** equipo dedicado que supervisa, detecta, investiga y responde en tiempo real, apoyado en SIEM y otras herramientas. Sus analistas deciden la reacción según procedimientos.
- **Falsos positivos:** eventos legítimos registrados como maliciosos; el analista los confirma y puede ajustar umbrales. Ejemplo: empleada que olvida su contraseña tras las vacaciones.
- **IA en detección:** automatiza registro y análisis, detecta anomalías de tráfico (por ejemplo, DDoS), potencia los SIEM (QRadar SIEM fija umbrales), permite a los analistas centrarse en alertas del sistema, y con ML aprende patrones de falsos positivos (por ejemplo, fallos de inicio desde una IP interna de confianza en horario laboral) para ajustar umbrales.

### 5. Respuesta a ataques

- **Marco de respuesta a incidentes del SANS Institute (seis fases):**
  1. Preparación: planificar recursos y procedimientos de prueba.
  2. Identificación: detectar el evento y confirmar que es un incidente real, no una falsa alarma.
  3. Contención: evitar que empeore (segregar redes, cerrar rutas de acceso o sistemas).
  4. Erradicación: eliminar por completo la presencia y el impacto (borrar o restaurar dispositivos); una erradicación incompleta provoca reapariciones.
  5. Recuperación: reanudar la actividad normal (retirar correcciones temporales, restaurar servicios).
  6. Reflexión (lecciones aprendidas): analizar la causa y la eficacia de la respuesta; sin cambios posteriores sería solo "lecciones identificadas".
  - Algunas fases se alargan según el incidente (por ejemplo, un dispositivo de almacenamiento perdido: erradicación corta y recuperación larga).
- **Preparación:** pruebas en papel (cuestionarios sobre preparación: personal clave, copias de seguridad, documentos de proceso), simulaciones teóricas (el personal simula la respuesta de principio a fin) y pruebas en vivo (las más realistas, desconectando sistemas críticos).
- **Continuidad del negocio:** seguir funcionando pese al incidente (respaldos de sitios, tecnología alternativa). **Recuperación ante desastres:** recuperarse tras un desastre, incluso partiendo casi de cero. Hoy un ciberataque puede ser tan destructivo como un desastre natural y más probable de afectar a toda una multinacional.
- **Beneficio de un equipo IR:** coste medio de una filtración de 3,62 M USD con capacidad de respuesta frente a 5,11 M USD sin ella (1,49 M USD o 34 % menos; IBM 2023).

### 6. Criptografía

- Comunicaciones seguras (con los personajes Alice, Bob y Eve como emisor, receptor y espía): **confidencialidad** (Eve no entiende el mensaje), **autenticidad** (Eve no puede suplantar a Alice) e **integridad** (Bob detecta si el mensaje fue modificado).
- **Cifrado:** convierte texto plano en texto cifrado con un cifrador y una clave; solo quien tiene la clave de descifrado puede revertirlo.
- **Simétrico:** misma clave para cifrar y descifrar; rápido y simple, pero exige compartir la clave. Ejemplo: rotación del alfabeto con clave +1 (HOLIDAY pasa a IPMJEBZ). **AES** es un algoritmo simétrico común que protege contraseñas y transacciones.
- **Asimétrico (clave pública):** par de claves generadas a la vez; la pública cifra y se comparte, la privada descifra y se mantiene en secreto. Permite comunicarse con quien nunca se ha intercambiado una clave y asegura que llegue al receptor correcto; es lo que hace viables las compras seguras por Internet. Flujo: Alice cifra con la clave pública de Bob, y Bob descifra con su clave privada.
- **Computación cuántica:** hoy no puede romper el cifrado moderno, pero podría hacerlo pronto al factorizar números primos grandes. La **criptografía postcuántica** propone cuatro familias: basada en retículos, basada en hash, multivariante y basada en códigos.

### 7. Inteligencia de amenazas

- **Inteligencia de amenazas:** datos recopilados y analizados para entender motivos y comportamiento de los actores de amenazas; se centra en TTP e IoC.
  - Táctica: el por qué (por ejemplo, escalar privilegios).
  - Técnica: el cómo (por ejemplo, eludir controles de acceso).
  - Procedimiento: la implementación concreta (por ejemplo, una herramienta específica).
  - IoC (indicadores de compromiso): firmas de actividad del atacante (IP, hashes de archivos, dominios); su presencia sugiere compromiso previo.
- **Beneficios:** advertencia temprana, IoC para reglas de detección, contexto para atribución y anticipación, y aprendizaje de otras organizaciones.
- **Fuentes:** plataformas de intercambio (IBM X-Force Exchange), conferencias (Black Hat, RSA Conference, CYBERUK), artículos y noticias (Security Intelligence, Krebs on Security, Graham Cluley) y avisos de proveedores (Microsoft, Google, Apple).
- **IA en inteligencia de amenazas:** NLP para extraer datos de amenazas de datos no estructurados (redes sociales, noticias), intercambio automatizado de inteligencia sin revelar datos sensibles y análisis predictivo (datos históricos más ML).
- Conclusión: defensas diseñadas para las amenazas reales, no solo para cumplir un estándar, algo clave en organizaciones con operaciones complejas o atípicas.

## Amenaza - Control

| Amenaza o riesgo | Control o defensa mencionada |
|---|---|
| Filtración de datos y sus costes | Resiliencia cibernética, estrategia de seguridad, capacidad de respuesta a incidentes |
| Superficie de ataque amplia (acceso remoto, dispositivos personales) | Reducir la superficie, restringir ubicaciones de acceso, vigilar el perímetro |
| Acceso externo a sistemas internos | DMZ con cortafuegos externo e interno |
| Credenciales robadas y daño amplio | Mínimo privilegio (limita el radio de explosión) |
| Software sin soporte o sin parches | Parches, versiones con soporte, controles compensatorios, escáner de vulnerabilidades |
| Malware | Antimalware basado en firmas; defensas de dispositivo |
| Actividad maliciosa no detectada | Registros a prueba de manipulaciones, monitorización de red, SIEM, SOC |
| Fuerza bruta contra cuentas | Alerta SIEM por umbral de inicios fallidos |
| DDoS | Detección de anomalías de tráfico con IA y contramedidas |
| Falsos positivos | Ajuste de umbrales, ML que aprende patrones legítimos |
| Interceptación o manipulación de mensajes | Cifrado simétrico (AES) y asimétrico |
| Computación cuántica | Criptografía postcuántica (retículos, hash, multivariante, códigos) |
| Incidente en curso | Fases de respuesta (identificación, contención, erradicación, recuperación) |
| Interrupción grave o desastre | Continuidad del negocio y recuperación ante desastres |
| Amenazas emergentes | Inteligencia de amenazas (IoC, advertencias, intercambio, análisis predictivo) |
| Fraude de desvío de pagos | No cubierto: solo se define y se cita su impacto |

## Herramientas / comandos / ejemplos

- **Antimalware:** Malwarebytes, McAfee Antivirus, Windows Defender Antivirus.
- **SIEM:** QRadar SIEM (IBM), con umbrales de alerta.
- **Prevención de pérdida de datos (DLP)** y **cortafuegos**: citados como productos de proveedores distintos.
- **AES:** algoritmo de cifrado simétrico.
- **Plataforma de intercambio:** IBM X-Force Exchange.
- **Ejemplo de registro (Apache):**
  ```
  9.12.156.2 - bob [11/Jan/2020:14:16:34 -0700] "GET /index.html HTTP/1.0" 200 4066
  ```
  Muestra IP, usuario, fecha y hora, petición, código de estado y tamaño de la respuesta.
- **Comandos:** no cubierto.

## Laboratorio (qué se hizo y resultado)

No cubierto: el material no incluye laboratorio.

## Mapeo a frameworks (NIST, MITRE ATT&CK, ISO 27001)

- **C2M2 (Cybersecurity Capability Maturity Model):** niveles MIL0 (sin prácticas), MIL1 (ad hoc, reactivas, sin procesos formales), MIL2 (proactivas, documentadas, con recursos) y MIL3 (integradas en la estrategia, roles claros, evaluación y mejora continua). La tabla resumen anunciada no está incluida en el material.
- **10 pasos del NCSC (Reino Unido):** ver el listado en "Estrategia de seguridad".
- **Respuesta a incidentes del SANS Institute:** seis fases descritas en "Respuesta a ataques".
- **NIST:** solo citado como fuente de la definición de criptografía; no se mapean controles.
- **MITRE ATT&CK e ISO 27001:** no cubierto (el material usa los términos TTP e IoC, pero sin referirse a ATT&CK).
- **RGPD:** mencionado como ley de privacidad con multas severas, no como framework de controles.

## Preguntas de repaso (5) y sus respectivas respuestas

1. **¿Cuáles son los dos mayores contribuyentes al coste de una filtración de datos según el informe de IBM de 2023?**
   La detección y la escalada (auditorías, análisis forense) y, en segundo lugar, la pérdida de negocio por daño a la reputación.

2. **¿Qué es el principio de mínimo privilegio y cómo reduce el riesgo?**
   Conceder a usuarios y aplicaciones solo los permisos mínimos para su función. Reduce la consecuencia de un ataque exitoso (radio de explosión) y por tanto el valor del riesgo.

3. **¿Cómo ayudan el SIEM y el SOC a detectar ataques y cómo se relacionan con los falsos positivos?**
   El SIEM agrega datos de toda la infraestructura y alerta por patrones o umbrales; el SOC es el equipo que investiga y responde a esas alertas. Los analistas confirman los falsos positivos (eventos legítimos marcados como maliciosos) y pueden ajustar umbrales; la IA y el ML ayudan a reducirlos.

4. **¿Cuáles son las seis fases de respuesta a incidentes de SANS y por qué importa una erradicación completa?**
   Preparación, identificación, contención, erradicación, recuperación y reflexión. Una erradicación incompleta suele provocar la reaparición del malware.

5. **¿En qué se diferencian el cifrado simétrico y el asimétrico?**
   El simétrico usa la misma clave para cifrar y descifrar (rápido, pero hay que compartir la clave); el asimétrico usa un par: la clave pública cifra y la privada descifra, lo que permite comunicarse de forma segura sin intercambio previo de claves.
