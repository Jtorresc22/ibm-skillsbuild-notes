# Cybersecurity Fundamentals - M02: Ciberseguridad a la ofensiva

## Resumen

El módulo describe cómo piensan y operan los atacantes: quiénes son (cinco grupos de actores de amenazas), qué ataques usan, cómo se estructura una intrusión (Cyber Kill Chain y MITRE ATT&CK) y de qué se financian. Después explica dos fases de preparación del ataque: la ingeniería social y la recopilación de información, tanto pública (OSINT) como técnica (escaneo). El enfoque ofensivo sirve para anticipar al atacante y diseñar mejores defensas. La IA aparece de forma transversal como multiplicador de la capacidad de los atacantes.

Nota de estructura: el material agrupa siete secciones internas (rotuladas "Módulo 1" a "Módulo 7") dentro de este único módulo.

## Conceptos clave

- **Actor de amenazas:** entidad (persona, grupo u organización) que supone un posible atacante, aunque aún no haya atacado.
- **Cinco grupos de actores:** script kiddies, hacktivistas, bandas criminales, hackers de Estado-nación y amenazas internas.
- **Hacker ético / investigador de seguridad ofensiva:** usa métodos de atacante para probar y fortalecer sistemas.
- **Cyber Kill Chain:** modelo de siete pasos secuenciales de un ataque.
- **MITRE ATT&CK:** matriz pública de tácticas (objetivos) y técnicas (medios) de los atacantes.
- **Ingeniería social:** manipular a personas mediante engaño para obtener información o acciones.
- **OSINT:** inteligencia obtenida de fuentes públicas.
- **Escaneo técnico:** sondeo de redes y dispositivos para conocer sistema operativo, servicios y vulnerabilidades.

## Detalle por tema

### 1. Grupos de actores de amenazas

| Grupo | Motivación | Recursos y rasgos | Idea defensiva del material |
|---|---|---|---|
| Script kiddies | Reputación, estatus, entretenimiento, venganza | Herramientas y exploits públicos, a veces chatbots de IA; poca pericia y fondos | Parches eficaces; ser un objetivo menos fácil que otros |
| Hacktivistas | Ideológica (cambio político o económico) | Herramientas básicas a gran escala, como DoS; aficionados más expertos que se suman en causas de actualidad; ejemplo: Anonymous | Plan para soportar un ataque prolongado |
| Bandas criminales | Dinero | Grupo de crecimiento más rápido; trabajo a tiempo completo, especialistas, intercambio en la dark web, venta de malware; ransomware y robo de datos o propiedad intelectual | Defensas efectivas en activos críticos |
| Hackers de Estado-nación | Objetivos políticos o estratégicos (espionaje, subversión, manipulación de información) | Alta formación, investigación avanzada, infraestructura especializada, respaldo político; IA y ML; más objetivos por el IoT | Defensas plenamente capaces y coordinadas |
| Amenazas internas | Dinero, resentimiento, notoriedad | Usan su propio acceso y permisos, rara vez técnicas; a veces ingeniería social o empleados extorsionados | Investigar al personal, buena gestión, controles técnicos; vigilar señales de advertencia |

- Señales de alerta de amenaza interna: trabajar en soledad, expresar resentimiento, rendimiento menor, actividades inexplicables. Los controles técnicos fallan a menudo porque el usuario conoce el sistema.
- Las categorías se mezclan (hacktivistas que reclutan script kiddies, Estados que contratan bandas) y algunos atacantes simulan ser menos avanzados, lo que dificulta la atribución.
- **Dark web:** parte de Internet accesible solo con navegadores especializados, con actividad cifrada, privada y anónima; usada por delincuentes y también por activistas para evitar persecución.
- **Investigador de seguridad ofensiva (hacker ético):** pone sus habilidades al servicio de la defensa.
- Ejemplo de amenaza interna del material: Edward Snowden (robo de archivos de la NSA).

### 2. Tipos de ciberataques

- **DoS:** interrupción total o parcial por exceso de tráfico o consumo de recursos. Ejemplo: bomba XML (un fragmento XML pequeño que se replica hasta agotar recursos).
- **DDoS:** el mismo efecto desde muchas fuentes a la vez, mediante una botnet (red de bots o zombis, dispositivos infectados controlados en remoto). La IA puede estimar cuántos bots hacen falta y vigilar su rendimiento.
- **Phishing:** mensajes que simulan una fuente fiable para inducir una acción (instalar malware, dar acceso, revelar datos). Combina ingeniería social y engaño técnico.
- **Spear phishing:** phishing dirigido a una persona, grupo u organización concretos, tras investigarlos (por ejemplo, llamada falsa del banco usando datos de redes sociales). La IA permite automatizar mensajes personalizados.
- **Malware:** software que daña datos o sistemas sin consentimiento informado, normalmente activado por una acción del usuario. Ejemplos: keyloggers (capturan pulsaciones) y ransomware (secuestra archivos y exige rescate).
- **MitM (intermediario):** el atacante se interpone en la comunicación cliente-servidor y ve todo lo que se intercambia. Ejemplo: wifi gratuito falso que puede redirigir a un login falso o insertar anuncios.
- **Ataque al DNS:** manipular o interrumpir la resolución de nombres de dominio (secuestro de dominios, envenenamiento de caché). Ejemplo: Roaming Mantis comprometió routers para redirigir a un sitio malicioso que instalaba el malware Wroba.
- **Inyección de SQL:** código malicioso insertado en consultas SQL, normalmente por la entrada de una página web; puede llegar a borrar la base de datos. Ejemplo: TalkTalk (2015), con cientos de miles de registros robados.
- **IA en los ataques:** automatización de tareas (por ejemplo, phishing masivo), evasión de detección (malware que se adapta con ML), identificación de objetivos y mejora de la ingeniería social con deepfakes de audio o vídeo.
- Conclusiones del material: los DoS aparecen a menudo en noticias, el phishing es el más eficaz a nivel personal y el malware crece y evoluciona.

### 3. Estructura de un ciberataque

- Los ataques suelen ser campañas largas y persistentes: si una técnica falla, el atacante cambia de técnica. Los marcos ayudan al defensor a anticipar el siguiente movimiento.
- **Cyber Kill Chain (Lockheed Martin):** siete pasos en orden, cada uno depende del anterior; permite ver el ataque como proceso y no como evento aislado (ver tabla en la sección de frameworks).
- **Puertas traseras (paso de instalación):** nuevas cuentas, programas de acceso remoto o nuevas vulnerabilidades; permiten seguir entrando aunque se parchee la vulnerabilidad original.
- **MITRE ATT&CK:** organización sin ánimo de lucro que recopiló TTP (tácticas, técnicas y procedimientos) reales y creó una matriz pública y gratuita. Columnas = tácticas (objetivo del atacante); elementos de cada columna = técnicas.

### 4. Ecosistema de la ciberdelincuencia

- Principal motivación: el dinero. Existe un mercado negro digital (foros y plataformas ilegales) donde se compran y venden herramientas y datos robados, se colabora, se aprende y se contrata a especialistas; es dinámico y reaparece cuando las autoridades cierran sitios.
- Tres vías de ingreso:
  - **Robo:** fraude o engaño más que intrusión directa en bancos (por ejemplo, estafas de soporte técnico).
  - **Trabajos por encargo:** servicios ilegales pagados por un cliente, como DoS contra un competidor, robo de propiedad intelectual o destrucción de bases de datos.
  - **Extorsión:** inutilizar sistemas (ransomware, que cifra archivos y vende la clave) o amenazar con divulgar datos sensibles.
- **Criptomonedas y blockchain:** la criptomoneda usa criptografía para asegurar transacciones y se apoya en blockchain, un libro contable distribuido y permanente. Bitcoin (2009) abrió paso a otras ("altcoins"). Son atractivas para el delito porque son anónimas y suelen estar descentralizadas, lo que dificulta el rastreo; se usan para cobrar rescates y blanquear dinero. Tienen ventajas legítimas (rapidez, coste, inclusión) y riesgos (volatilidad, regulación).

### 5. Ingeniería social

- Uso de engaño para que alguien revele información o actúe de forma insegura; en persona, por teléfono o en línea. Ejemplos: estafas y **tailgating** (entrar a un área segura siguiendo a una persona autorizada).
- **Por qué funciona:**
  - Naturaleza humana y normas sociales (por ejemplo, colega "en apuros").
  - Confianza y autoridad (falso correo del CEO).
  - Manipulación emocional: miedo, curiosidad, excitación (falso premio de lotería).
  - Falta de concienciación (falso aviso del banco para cambiar la contraseña).
- **Rasgos de un ataque:** investigación previa, ejecución con confianza (a menudo en varios intercambios) y plausibilidad.
- **Defensa personal:** si algo parece demasiado bueno para ser verdad, probablemente lo es; cuestionar peticiones inusuales, pedir explicaciones o informar, y verificar antes de dejar pasar a alguien.
- **Defensa organizacional (proceso, formación, tecnología):** políticas de uso aceptable y manejo de información; formación periódica; filtros de spam y antimalware.
- **Pistas de phishing:** correo no esperado o con presión de urgencia, remitente desconocido, saludo genérico, errores de gramática, petición de datos bancarios o contraseñas, adjuntos no solicitados, lenguaje alarmante y URL sospechosas (sin https o con errores como "paypall").
- Ante un posible phishing: no responder, no hacer clic ni abrir adjuntos, reportarlo como spam y, si hay duda, contactar al remitente por un canal de confianza o entrar al servicio desde la dirección conocida.

### 6. OSINT

- Información de fuentes públicas (blogs, noticias, redes). La puede obtener cualquiera (periodistas, investigadores, atacantes) y suele ser más barata, fácil, legal e **indetectable para el objetivo** que el hackeo, el phishing o el malware.
- **Fuentes comunes:**
  - Sitio web de la empresa, con Google hacking y Wayback Machine para versiones antiguas.
  - Medios y analistas.
  - Redes sociales (fotos de credenciales, diagramas de red, contraseñas en notas).
  - Registros públicos (hospitalarios, censo electoral, bolsa).
  - Foros.
  - Ofertas de empleo (revelan software usado).
  - Registros DNS y WHOIS (datos de registro de dominios y subdominios).
- **Pautas:** reunir mucha información, contrastar varias fuentes (no fiarse de una sola; que se oculte información también es un dato) y no frustrarse (las investigaciones pueden tardar semanas).
- **Agregación de datos:** unir pequeñas piezas inofensivas revela información sensible (ejemplo: 100 empleados revelan cada uno el 1 % de un secreto). Las organizaciones deben diseñar políticas de información pensando en OSINT y publicar solo lo necesario. La buena seguridad operativa explica que algunos objetivos tengan poca información pública.

### 7. Escaneo técnico

- Objetivo del atacante en la fase de reconocimiento: saber qué sistema operativo usa un dispositivo, qué servicios ejecuta y si alguno es vulnerable a exploits conocidos. Las mismas técnicas las usan los administradores para gestionar la red.
- **Prueba de ping:** envía un paquete ICMP de solicitud de eco; una respuesta de eco indica que el equipo probablemente está activo. Repetida en barrido, cuenta dispositivos. El TTL baja en uno por cada router, de modo que indica la "distancia" (ejemplo: de 120 a 108 son 12 saltos).
- **Traceroute:** envía paquetes con TTL variable; los routers intermedios devuelven un error cuando el TTL llega a cero y así se mapean los nodos entre origen y destino.
- **Escaneo de puertos:** identifica puertos abiertos de un host. Abierto = acepta conexión; cerrado = rechaza; filtrado = no responde (posible filtro de paquetes o cortafuegos). TCP tiene 65 536 puertos; del 0 al 1023 son "conocidos"; 1024 a 49 151 pueden estar registrados. Ejemplos: 80 (HTTP), 445 (archivos de Windows, objetivo de WannaCry), 3389 (RDP).
- **Escaneo de vulnerabilidades:** incluye escaneo dinámico (simula técnicas como inyección SQL), detección de versiones y detección de sistema operativo. Sirve a organizaciones (escaneos periódicos) y a atacantes.
- **Shodan:** motor de búsqueda de dispositivos conectados a Internet, con miles de millones de registros de escaneo.
- **Análisis de red (Nmap/Zenmap):** ver herramientas.
- **IA en el escaneo:** categoriza y prioriza vulnerabilidades por gravedad, aprende de escaneos previos, acelera el análisis y reduce errores humanos.
- Advertencia del material: el escaneo dinámico puede ser ilegal en algunos países; escanear solo con consentimiento del propietario, ya que un análisis de vulnerabilidades suele interpretarse como preparación de un ataque.

## Amenaza - Control

| Amenaza | Control o defensa mencionada |
|---|---|
| Script kiddies con exploits públicos | Programa eficaz de aplicación de parches; defensas que hagan al objetivo menos atractivo |
| Hacktivistas (ataques prolongados) | Plan y métodos para resistir un ataque sostenido |
| Bandas criminales y ransomware | Defensas efectivas en activos críticos |
| Hackers de Estado-nación | Defensas plenamente capaces y coordinadas |
| Amenazas internas | Investigación de empleados, gestión eficaz, controles técnicos, vigilancia de señales de advertencia |
| Ingeniería social | Políticas (proceso), formación periódica, filtros de spam y antimalware |
| Phishing | Revisar pistas del mensaje, verificar URL, no responder ni hacer clic, reportar como spam, verificar por canal de confianza |
| Tailgating y peticiones sospechosas | Pedir explicaciones, informar y verificar antes de permitir el acceso |
| Fuerza bruta (táctica de acceso con credenciales) | Bloqueo de cuentas (el ejemplo parte de su ausencia) |
| OSINT y agregación de datos | Políticas de gestión de la información, publicar lo mínimo necesario, buena seguridad operativa |
| Escaneo de puertos | Cerrar o bloquear puertos innecesarios sin impedir el acceso legítimo; filtros de paquetes |
| Vulnerabilidades expuestas | Escaneos periódicos propios de vulnerabilidades |
| Ataques con IA | Incorporar IA a las estrategias de ciberdefensa |
| DoS/DDoS, MitM, ataques al DNS, inyección de SQL | No cubierto: el material describe el ataque sin detallar contramedidas |

## Herramientas / comandos / ejemplos

- **Comandos citados (Windows):** `ping target_name` y `tracert target_name`.
- **Nmap:** escáner de red gratuito y de código abierto (Windows, macOS, Linux). Escaneo de puertos como función principal; también ruta de red hasta el host, detección de versiones y de sistema operativo, e identificación de cortafuegos. Opera por línea de comandos.
- **Zenmap:** interfaz gráfica oficial de Nmap; permite elegir opciones y muestra el comando Nmap equivalente, útil para aprender la sintaxis.
- **Shodan:** buscador de dispositivos conectados.
- **WHOIS:** consulta de datos de registro de dominios.
- **Wayback Machine y Google hacking:** recuperar sitios antiguos y buscar archivos expuestos.
- **QRadar Advisor with Watson (IBM):** herramienta con IA/ML que analiza incidentes, identifica amenazas, investiga y descarta falsos positivos para que los analistas se centren en las amenazas confirmadas.
- **Ejemplos del material:** bomba XML, Roaming Mantis y Wroba, TalkTalk 2015, WannaCry en el puerto 445, URL falsa "paypall".


## Mapeo a frameworks

**Lockheed Martin Cyber Kill Chain** (no figura en la lista de la plantilla, pero es un framework citado):

| Paso | Descripción |
|---|---|
| 1. Reconocimiento | Recopilar información del objetivo |
| 2. Equipamiento | Preparar o conseguir el malware para la vulnerabilidad elegida |
| 3. Entrega | Hacerlo llegar (correo, descargas web, USB) |
| 4. Explotación | El objetivo lo activa y se explota la vulnerabilidad con un exploit |
| 5. Instalación | Lograr persistencia (puertas traseras) |
| 6. Comando y control (C2) | Canal de comunicación con los sistemas comprometidos |
| 7. Acciones sobre los objetivos | Robar o modificar datos, destruir elementos clave |

**MITRE ATT&CK:** estructura en tácticas y técnicas. Ejemplo del material: táctica Acceso con credenciales (Credential Access, TA0006) y técnica Fuerza bruta (Brute Force, T1110). Se menciona el extracto gráfico de la matriz, que no está incluido en el material.



## Preguntas de repaso (5) y sus respectivas respuestas

1. **¿Por qué se habla de "actor de amenazas" y no solo de "atacante"?**
   Porque el término enfatiza la amenaza potencial: una entidad puede tener intención de atacar sin haberlo hecho todavía.

2. **¿Qué diferencia hay entre un DoS y un DDoS y qué papel tiene la botnet?**
   El DoS interrumpe un sistema total o parcialmente; el DDoS lo hace desde múltiples fuentes simultáneas. La botnet es el conjunto de bots (dispositivos infectados controlados en remoto) que envían tráfico a la vez para saturar al objetivo.

3. **¿Cuáles son los siete pasos de la Cyber Kill Chain y por qué importa el orden?**
   Reconocimiento, equipamiento, entrega, explotación, instalación, comando y control, y acciones sobre los objetivos. El orden importa porque cada paso depende de que se haya completado el anterior, por lo que permite ver el ataque como un proceso.

4. **¿Qué tres vías usan los ciberdelincuentes para obtener dinero y por qué prefieren las criptomonedas?**
   Robo, trabajos por encargo y extorsión. Prefieren las criptomonedas porque son anónimas y suelen ser descentralizadas, lo que dificulta el rastreo por las autoridades (por ejemplo, rescates de ransomware y blanqueo de dinero).

5. **¿Qué significan los estados abierto, cerrado y filtrado de un puerto en un escaneo?**
   Abierto: acepta la conexión. Cerrado: la rechaza. Filtrado: el host no responde, lo que puede indicar que un filtro de paquetes (cortafuegos) bloquea el acceso.
