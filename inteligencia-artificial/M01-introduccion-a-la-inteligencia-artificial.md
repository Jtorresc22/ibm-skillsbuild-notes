# Fundamentos de la IA: las bases para comprender la IA - M01 Introducción a la inteligencia artificial

## Resumen
La IA es la capacidad de las máquinas de realizar tareas que normalmente exigen inteligencia humana. Se manifiesta en tres capacidades (lenguaje, percepción, toma de decisiones) y en cuatro formas (generativa, predictiva, para la toma de decisiones, de visión artificial), y opera en dos pasos: análisis y predicción. El módulo repasa cómo los humanos trabajan con información, las eras del procesamiento de datos y por qué la complejidad actual de los datos (no estructurados, ocultos) hace necesarios sistemas probabilísticos. En el trabajo, la IA automatiza y aumenta, pero el juicio y la responsabilidad siguen siendo humanos.

## Conceptos clave
- IA, algoritmo, capacidades de la IA.
- Automatización vs. aumento.
- Cuatro formas de IA: generativa, predictiva, para la toma de decisiones, de visión artificial.
- Análisis y predicción.
- Cinco funciones humanas de datos: contar, registrar, analizar y decidir, reconocer patrones, comunicar.
- Tres eras: tabulación, programación, IA.
- Sistemas basados en reglas y lógica de ramificación.
- Etapas de la IA: thinking machines, sistemas de programa fijo, learning machines, computación en la nube.
- Datos estructurados, no estructurados, semiestructurados y metadatos.
- Datos ocultos.
- Sistemas deterministas vs. probabilísticos.
- Tres fortalezas de la IA: detectar patrones, analizar volúmenes masivos, aprender de forma continua.

## Detalle por tema

### Lección 1: qué es la IA
- **Definición:** capacidad de las máquinas para reconocer patrones, tomar decisiones o comprender lenguaje; usa algoritmos para procesar grandes volúmenes de información (asistentes de voz, recomendaciones, detección de fraude).
- **Automatización y aumento:** la automatización se encarga de tareas repetitivas y predecibles (clasificar archivos, informes rutinarios); el aumento apoya el pensamiento, la decisión y la creatividad. Suelen darse a la vez. Regla común: el humano es la autoridad final; la IA aporta velocidad, la persona aporta dirección.
- **Ejemplo con IBM Bob** (socio de IA para desarrollo de software), en cinco pasos: 1) crea la base del código y la configuración, el desarrollador revisa; 2) propone una solución a un error, el desarrollador investiga la causa de fondo antes de aplicarla; 3) genera escenarios de prueba de seguridad, el desarrollador los revisa; 4) escribe documentación, el desarrollador la pule; 5) sugiere mejoras al código antiguo, el desarrollador decide si sirven.
- **Otros roles:** gerente de proyecto (resume transcripciones; él decide prioridades), analista de ciberseguridad (la IA prioriza alertas; él evalúa el riesgo), analista de datos (la IA traduce lenguaje natural a consultas; él valida supuestos), educador (la IA genera opciones; él da significado y contexto).
- **Capacidades** (funciones básicas para las que se diseña el sistema):
  - Lenguaje: leer, escribir, traducir, responder (ej. chatbot de una tienda).
  - Percepción: analizar imágenes, sonidos y otros datos sensoriales (ej. desbloqueo facial).
  - Toma de decisiones: analizar datos, ponderar opciones y recomendar (ej. recomendación de productos).
- **Formas de IA:**
  - Generativa: crea texto, imágenes o música nuevos a partir de lo aprendido; útil en marketing, diseño, desarrollo.
  - Predictiva: usa datos históricos para pronosticar eventos o comportamientos; finanzas, salud, retail.
  - Para la toma de decisiones: evalúa datos y decide o recomienda según reglas programadas o modelos aprendidos; logística, finanzas, salud.
  - De visión artificial: interpreta imágenes y video (rostros, objetos, escenas); seguridad, manufactura, salud.
- **Cómo funciona:** (1) análisis, donde examina muchos datos para hallar patrones; (2) predicción, donde la IA generativa usa probabilidades estadísticas para anticipar las palabras o imágenes más probables.

### Lección 2: de los problemas de datos a las capacidades de la IA
- **Cinco funciones humanas de datos** (con su versión con IA):
  - Contar: piedras del pastor, hojas de cálculo, visión artificial que cuenta alumnos en una entrada.
  - Grabar y recuperar: tablillas de barro, bases de datos médicas, asistente que resume una reunión.
  - Analizar y decidir: experiencia del agricultor, estadísticas del entrenador, IA que analiza miles de reseñas.
  - Reconocer patrones: reconocer a un amigo por su forma de caminar; filtro de spam por reglas; auto inteligente que reconoce señales y peatones.
  - Comunicar y traducir: pinturas rupestres, imprenta, correo; apps de pronunciación, IA generativa para historias o música.
- **Tres eras del procesamiento de datos:**
  - Tabulación: máquinas para estructurar datos (ábaco usado por recaudadores chinos hace más de 2000 años).
  - Programación: computadoras que ejecutan programas. ENIAC (1946) hacía en 30 segundos lo que costaba 12 horas a mano; la IBM 7030 (1960) resolvía en un día lo que otras tardaban seis meses.
  - IA: el término "inteligencia artificial" se acuñó en 1956 en Dartmouth College (John McCarthy, Marvin Minsky y colegas); a mediados de los 90 la mayor potencia de cómputo permitió problemas más complejos.
- **Algoritmo:** conjunto de reglas o procedimiento paso a paso para realizar una tarea o resolver un problema.
- **Sistemas basados en reglas:** deciden con reglas fijas (tipo "si-entonces"). Sirven para tareas simples y repetitivas, pero no aprenden ni se adaptan: si el caso sale de las reglas, se bloquean.
- **Lógica de ramificación:** secuencia de pasos lógicos que explora opciones para alcanzar una meta (ej. buscar movimientos para ganar un juego). Más flexible que las reglas, pero tampoco aprende de los datos. Estas limitaciones llevaron al machine learning.
- **Etapas de desarrollo:**
  - Thinking machines: la idea de dispositivos que razonan; la máquina de Turing (década de 1930).
  - Sistemas de programa fijo: calculadoras y tabuladoras con instrucciones detalladas, sin adaptación.
  - Learning machines: aprenden de datos históricos y mejoran (reconocer voz, imágenes, motores de recomendación como Netflix o Spotify).
  - Computación en la nube: almacenar y procesar datos a escala global; hace accesible la IA avanzada (ej. procesamiento de lenguaje natural).

### Lección 3: la complejidad de los datos hoy
- **Dato:** información que se recopila, almacena y usa para analizar, decidir o comunicar en sistemas digitales.
- **Tipos:**
  - Estructurados: organizados en filas y columnas (nombres, fechas, cifras bursátiles).
  - No estructurados: sin organización incorporada (imágenes, mensajes, comentarios de clientes, historiales médicos).
  - Semiestructurados: intermedios; no caben en tablas pero tienen elementos que los organizan (un video con hashtag, marca de tiempo y ubicación).
  - Metadatos: información que describe otros datos (fecha, tamaño, autor, etiquetas); organizan los semiestructurados.
- **Escala:** se generan 2,5 quintillones de bytes por día, equivalente a unos 250 000 millones de películas HD diarias.
- **Por qué cuestan los no estructurados y semiestructurados:** inconsistencia (sin formato predecible, p. ej. feedback en distintos idiomas) y variabilidad (texto, imagen, audio, video requieren procesamiento y almacenamiento distintos).
- **Datos ocultos:** información que ya existe en una organización pero no se usa ni analiza porque es difícil de procesar con herramientas tradicionales (respuestas largas, llamadas grabadas, transcripciones de chat, videos de investigación, archivos escaneados). No son un tipo de dato aparte. Analizarlos permite entender mejor al cliente, detectar problemas antes, hallar patrones y mejorar productos.
- **Sistemas deterministas:** reglas estrictas preprogramadas; misma entrada, misma salida. Requieren datos limpios y consistentes y fallan ante errores tipográficos, formatos distintos o información incompleta (una base de datos busca coincidencias exactas).
- **Sistemas probabilísticos:** modelos estadísticos que calculan la probabilidad de distintos resultados; manejan datos desordenados e incertidumbre (entienden que "gr8 product!", "gran producto" y "excelente artículo" expresan sentimiento positivo).
- **Tres fortalezas de la IA:**
  - Detecta patrones: creación de contenido, imágenes médicas, pronóstico de mercado.
  - Analiza cantidades masivas: optimización de cadena de suministro, generación de documentos legales, inspección de calidad.
  - Aprende continuamente: detección de fraude, contenido personalizado, navegación autónoma.

## Intuición vs. formalismo
- **IA.** Intuición: máquinas que hacen cosas que antes requerían "pensar". Formal: capacidad de las máquinas para realizar tareas que normalmente requieren inteligencia humana, como reconocer patrones, decidir o comprender lenguaje.
- **Algoritmo.** Intuición: una receta de cocina. Formal: conjunto de reglas o procedimiento paso a paso para resolver un problema.
- **Capacidades de la IA.** Intuición: lo que el sistema "sabe hacer". Formal: funciones básicas para las que está diseñado; se agrupan en lenguaje, percepción y toma de decisiones.
- **Automatización vs. aumento.** Intuición: el calendario que agenda solo vs. el asistente que te ayuda a elegir qué reuniones importan. Formal: manejo de tareas repetitivas y predecibles frente a apoyo al pensamiento, decisión y creatividad.
- **IA generativa.** Intuición: aprende de ejemplos y produce algo parecido, no copiado. Formal: sistemas que crean contenido nuevo (texto, imágenes, música) aprendiendo de grandes conjuntos de datos existentes, mediante probabilidades estadísticas.
- **IA predictiva.** Intuición: mirar el pasado para anticipar el futuro. Formal: uso de datos históricos para pronosticar eventos, tendencias o comportamientos.
- **Sistema basado en reglas.** Intuición: seguir un manual al pie de la letra. Formal: sistema que decide con reglas fijas y explícitas, sin aprender.
- **Datos estructurados vs. no estructurados.** Intuición: una hoja de cálculo vs. una carpeta de fotos y notas sueltas. Formal: datos organizables en filas y columnas vs. datos sin organización incorporada que las herramientas convencionales procesan con dificultad.
- **Datos ocultos.** Intuición: archivos guardados que nadie vuelve a abrir. Formal: información existente en una organización que no se usa ni analiza, normalmente por la dificultad de procesarla.
- **Determinista vs. probabilístico.** Intuición: diagrama de flujo rígido vs. "lo más probable es que...". Formal: reglas preprogramadas con resultado idéntico ante entrada idéntica vs. modelos estadísticos que estiman probabilidades de resultados.

## Supuestos y limitaciones
- Sistemas basados en reglas: no aprenden ni se adaptan; se bloquean fuera de sus reglas; inadecuados para voz o imágenes.
- Lógica de ramificación: más flexible, pero no aprende de los datos por sí misma.
- Sistemas deterministas: requieren datos limpios, estructurados y con formato consistente; no manejan casos extremos ni contexto.
- La IA no entrega un resultado "final": siempre requiere revisión y aprobación humana.

## Aplicaciones y ejemplos
- Desarrollo de software con IBM Bob; resumen de reuniones; priorización de alertas de seguridad; consultas de datos en lenguaje natural.
- Chatbot de tienda, desbloqueo facial, recomendación de productos.
- Conteo de alumnos por visión artificial, resumen automático de reuniones, análisis de reseñas, filtros de spam.
- Imágenes médicas, optimización de inventario, inspección de calidad, detección de fraude, vehículos autónomos.

## Consideraciones éticas
- Uso responsable: tratar la salida de la IA como borrador, aplicar juicio y contexto, y mantener la responsabilidad en la persona.
- El material de este módulo no desarrolla más temas éticos (los pilares de confianza aparecen en M02).

## Herramientas / código
- **IBM Bob:** herramienta de IA para desarrollo de software presentada como ejemplo de colaboración; no hay código en el material.

## Preguntas de repaso
1. ¿Cuál es la diferencia entre automatización y aumento?
   **R:** La automatización maneja tareas repetitivas y predecibles; el aumento apoya el pensamiento, la decisión y la creatividad. En ambos, la persona conserva la decisión final.
2. Menciona las tres capacidades de la IA y un ejemplo de cada una.
   **R:** Lenguaje (chatbot que responde horarios), percepción (reconocimiento facial para desbloquear un dispositivo), toma de decisiones (recomendación de productos según compras previas).
3. ¿Por qué los sistemas basados en reglas dieron paso al machine learning?
   **R:** Porque no aprenden ni se adaptan: fallan ante casos no previstos y no pueden con tareas complejas como reconocer imágenes o entender el habla.
4. ¿Qué son los datos ocultos y por qué importan?
   **R:** Información que ya existe en una organización pero no se analiza por ser difícil de procesar (llamadas grabadas, archivos escaneados). Contiene insights sobre clientes, problemas y patrones útiles para decidir mejor.
5. ¿En qué se diferencia un sistema determinista de uno probabilístico?
   **R:** El determinista aplica reglas fijas y da siempre el mismo resultado ante la misma entrada, pero falla con datos inesperados; el probabilístico estima probabilidades y tolera datos desordenados o ambiguos.
