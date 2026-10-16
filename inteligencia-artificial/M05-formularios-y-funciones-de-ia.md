# Fundamentos de la IA: las bases para comprender la IA - M05 Formularios y funciones de IA

## Resumen
El módulo recorre las cuatro formas principales de IA: predictiva (qué pasará), para la toma de decisiones (qué conviene hacer), de visión artificial (qué hay en una imagen) y generativa (crear contenido nuevo). Para cada una se explican su función, sus usos y cómo aplicar los cinco pilares de confianza en un caso concreto. También se cubren los cinco pasos de la visión artificial, la IA multimodal, la diferencia entre IA generativa y motor de búsqueda, y los cinco componentes de una instrucción eficaz.

## Conceptos clave
- Capacidades (lenguaje, percepción, decisión) y formas de IA; análisis y predicción.
- IA predictiva: insights y recomendaciones, análisis de riesgos, planificación y previsión.
- IA para la toma de decisiones: seleccionar, optimizar, automatizar.
- Visión artificial: cinco pasos; reconocer formas, clasificar objetos, generar imágenes.
- IA generativa: multimodalidad, cuatro tipos de tarea, diferencia con buscadores.
- Instrucción (prompt): rol, contexto, tarea, resultado, restricciones.
- Cinco pilares de confianza aplicados a cada forma de IA.

## Detalle por tema

### Lección 1: formas de inteligencia artificial
- Repaso: capacidades de lenguaje, percepción y toma de decisiones; las formas de IA las aplican de distinto modo; el flujo típico es análisis (hallar patrones) y predicción (generar lo más probable).
- **Caso del video (coordinador de contenido):** el planificador de tareas usa IA para la toma de decisiones (ordena tareas por plazos, complejidad y prioridades); la visión artificial revisa fotogramas para elegir las mejores tomas (detección de bordes, análisis de brillo, composición); la IA generativa redacta resúmenes y subtítulos; la IA predictiva recomienda formatos y horarios de publicación. La IA apoya la creatividad sin reemplazarla.
- **Predictiva:** analiza datos pasados para pronosticar (ventas, demanda, fallos de equipos, planificación de inventario). Ej.: retail que pide inventario según lo que se venderá la próxima temporada.
- **Para la toma de decisiones:** compara datos, pondera resultados y recomienda o automatiza acciones, y reduce error humano en situaciones rutinarias o de presión. Ej.: naviera que elige la ruta más rápida según tráfico, clima y plazos.
- **De visión artificial:** identifica objetos, personas y movimientos (clasificar paquetes, reconocer rostros, leer radiografías, controlar calidad en líneas de ensamblaje).
- **Generativa:** crea texto, imágenes, música o código (correos, informes, fragmentos de código, ideas de diseño).

### Lección 2: IA predictiva
- Usa patrones de datos históricos y a veces en tiempo real para estimar lo probable (demanda, duración de trabajos, abandono de clientes, fallas de equipos). Combina análisis estadístico y machine learning.
- Sus resultados son estimaciones (puntuaciones, probabilidades, rangos) y dependen de la calidad y relevancia de los datos. Complementa el juicio humano y otras formas de IA.
- **Tres roles:**
  - Ofrecer insights y recomendaciones (anticipar que el calor sube las ventas de helado y surtir antes).
  - Análisis de riesgos: estimar qué puede salir mal y con qué probabilidad (banco que evalúa el incumplimiento de un préstamo).
  - Planificación y previsión: apoyar decisiones sobre presupuesto, personal o suministros (pronóstico de tiempos de entrega).
- **Pilares de confianza (caso: banco y solicitudes de préstamo):**
  - Imparcialidad: comparar decisiones entre grupos y corregir si un origen específico recibe más riesgo.
  - Robustez: probar con casos inusuales, datos de mala calidad o intentos de manipulación; usar solo información relevante.
  - Explicabilidad: poder responder "¿por qué estoy en alto riesgo?" (ej. tres incumplimientos en cinco años).
  - Transparencia: documentar fuentes de datos, propósito, características clave, limitaciones y desempeño por grupos.
  - Privacidad: recopilar solo lo necesario, proteger con seguridad sólida, informar al cliente y permitir corregir datos erróneos.

### Lección 3: IA para la toma de decisiones
- Convierte datos y metas en acción: evalúa compensaciones, respeta restricciones y reglas, y recomienda el siguiente paso; a veces ejecuta respuestas predefinidas cuando la velocidad importa.
- **Tres funciones:** seleccionar la mejor acción, optimizar resultados al asignar tiempo, costo o capacidad limitados, y automatizar decisiones (aprobar, reenviar o bloquear según políticas). Los resultados incluyen opciones jerarquizadas con justificación, cronogramas o asignaciones optimizadas; siempre bajo objetivos y límites definidos por el usuario, que conserva la posibilidad de revisar, aprobar o anular.
- **Predictiva vs. decisión:** la predictiva responde "¿qué pasará?" o "¿cuánto esperar?" y no decide; la de decisión responde "¿qué opción elegir?", ordena alternativas y explica su razonamiento. Suelen combinarse: predecir la demanda y luego asignar inventario y programar entregas.
- Usa algoritmos de optimización. Ejemplos: recomendación en streaming, distribución de electricidad en una red, bloqueo instantáneo de transacciones sospechosas.
- **Pilares de confianza (caso: gestión agrícola):** imparcialidad (no favorecer a ciertas cooperativas), robustez (simular fallas de sensores e intrusiones; mismo perfil de riesgo, mismo trato), explicabilidad (por qué se rechazó un riego, con métricas de campo), transparencia (origen de datos y métricas de auditoría; más exigente que en predictiva porque las salidas determinan operaciones reales), privacidad (limitar el uso de registros a lo necesario, con controles de acceso y control para las partes interesadas). Se sugiere reforzar vías de apelación.

### Lección 4: IA de visión artificial
- **Definición:** tecnología que permite a las máquinas interpretar y reconocer información visual de imágenes y videos mediante algoritmos y reconocimiento de patrones. A diferencia de la visión humana, usa modelos matemáticos y grandes conjuntos de datos.
- **Cinco pasos:** captura de imágenes (cuadrícula de píxeles); preprocesamiento (quitar desenfoque, ajustar color, nitidez); detección de características (bordes, esquinas, patrones); reconocimiento de patrones (comparar con muchos ejemplos); resultado de la decisión (etiquetar, alertar, desbloquear).
- **Tres habilidades (video del escáner de retina):** reconocer formas (interpreta píxeles, círculos, curvas, bordes), clasificar objetos (categorizar por rasgos distintivos y compararlos con una base de datos para autorizar o no) y generar imágenes nuevas (ej. patrones de ojo simulados para probar el sistema).
- **Usos prácticos:** identificar objetos (plantas, productos, piezas de almacén); mejorar contenido con nuevos gráficos; accesibilidad (describir escenas, leer texto en voz alta, ayudar a navegar).
- **Pilares de confianza (caso: app de arte para un festival):** equidad (reconocer arte de muchos artistas y culturas), robustez (resistir trucos como una pegatina en el mural y funcionar con poca luz o multitudes), explicabilidad (indicar si identificó por color, forma o estilo), transparencia (avisar cuándo usa la cámara y qué recopila), privacidad (recopilar solo lo necesario, no almacenar datos personales, permitir borrar fotos).
- Pregunta abierta del material: ¿usar reconocimiento facial en espacios públicos sin consentimiento viola la privacidad o implica mal uso de datos?

### Lección 5: IA generativa
- **Definición:** sistemas que, mediante modelos de aprendizaje profundo y sus datos, crean contenido original (texto, imagen, video, audio, software) en respuesta a una instrucción. Sintetizan lo aprendido en lugar de copiar. Sus resultados son probabilísticos y pueden contener errores, de modo que requieren revisión humana, verificación de datos y etiquetado claro.
- **Multimodalidad:** trabajo con varios tipos de datos en un flujo único. Patrones comunes: texto a imagen, texto a audio, imagen a texto, audio a texto, video a texto.
- **Cuatro tipos de tarea:**
  - Creación de contenido: artículos, correos, materiales de capacitación, descripciones de producto.
  - Resolución de problemas (creativos o de patrones): distintas formas de explicar algo complejo; no destaca en lógica compleja ni en decisiones.
  - Generación de ideas: títulos, temas, nombres.
  - Personalización: adaptar tono, estilo o nivel de lectura a cada audiencia.
- **Frente a un motor de búsqueda:**
  - El buscador encuentra información existente: la indexa (guarda contenido, palabras y estructura de las páginas) y ordena resultados con palabras clave, etiquetas semánticas y algoritmos de clasificación; conviene cuando se necesita una fuente directa, una cita o una actualización reciente.
  - La IA generativa crea contenido nuevo a partir de patrones de enormes volúmenes de datos, sin señalar una fuente específica; conviene como punto de partida, resumen o respuesta creativa.
  - La tabla comparativa del módulo **no está cubierta** en el material.
- **Aplicaciones:** negocios (correos, marketing, presentaciones, resúmenes), educación (pruebas, lecturas, resúmenes), arte y creatividad (conceptos iniciales de historias, canciones o diseños), entretenimiento (guiones, personajes, historias interactivas).
- **Instrucción eficaz (cinco componentes):** rol, contexto, tarea, resultado y restricciones. Ejemplo reformulado: "Actúa como orientador laboral (rol). Me preparo para una entrevista en una empresa de tecnología (contexto). Propón cinco preguntas conductuales típicas con un consejo para cada una (tarea). Preséntalas en lista numerada, con una línea de consejo debajo (resultado). Cada consejo debe tener menos de 200 palabras (restricciones)."
- **Pilares de confianza:** imparcialidad (datos variados, probar sesgos de representación), robustez (deepfakes, comentarios falsos, suplantación; probar contra instrucciones dañinas y añadir salvaguardas), explicabilidad (etiquetar contenido generado y ofrecer cómo verificarlo), transparencia (informar datos usados y propósito; marcar qué partes creó la IA), privacidad (anonimizar datos de entrenamiento y vigilar que no se filtre información personal).

## Intuición vs. formalismo
- **IA predictiva.** Intuición: mirar atrás para anticipar. Formal: uso de análisis estadístico y machine learning para identificar patrones, anticipar comportamientos y predecir eventos futuros.
- **IA para la toma de decisiones.** Intuición: elegir la mejor jugada entre varias. Formal: evalúa múltiples acciones posibles y elige la óptima según factores como eficiencia, exactitud y resultados sugeridos.
- **IA de visión artificial.** Intuición: ver sin ojos, interpretando píxeles. Formal: tecnología que permite a las máquinas interpretar y reconocer información visual de imágenes digitales y videos con algoritmos y reconocimiento de patrones.
- **IA generativa.** Intuición: una máquina que redacta y dibuja a partir de lo que aprendió. Formal: sistemas que usan modelos de aprendizaje profundo y sus datos para crear contenido original en respuesta a una instrucción.
- **IA multimodal.** Intuición: entender y combinar texto, imagen, audio y video a la vez. Formal: IA que crea contenido nuevo a partir de diversas fuentes y tipos de datos.
- **Instrucción (prompt).** Intuición: la petición que le haces a la IA. Formal: declaración de entrada, pregunta o indicación que se proporciona a un sistema de IA generativa para guiar la creación de un resultado específico.
- **Indexación.** Intuición: el catálogo que usa el buscador para no recorrer toda la web cada vez. Formal: registro del contenido, palabras y estructura de las páginas en una base de datos para encontrar coincidencias rápido.

## Supuestos y limitaciones
- Predictiva: los resultados son estimaciones; dependen de la calidad y relevancia de los datos.
- Decisión: opera dentro de objetivos y límites definidos por el usuario; no sustituye a las personas.
- Visión artificial: sensible a ángulos inusuales, poca luz, multitudes y trucos visuales.
- Generativa: probabilística, puede errar; no destaca en lógica compleja ni decisiones; requiere revisión, verificación de datos y etiquetado.
- Buscadores: devuelven solo un subconjunto de la información disponible.
- Otro aspecto del material: algunas tareas siguen requiriendo experiencia en la materia, pensamiento crítico o comprensión de necesidades humanas complejas.

## Aplicaciones y ejemplos
- Pronóstico de ventas, mantenimiento predictivo, riesgo crediticio, tiempos de entrega.
- Rutas de entrega, distribución de energía, bloqueo de fraude, recomendación de contenido.
- Escáner de retina, desbloqueo facial, lectura de radiografías, control de calidad, accesibilidad, inventario por cámaras.
- Redacción de correos y descripciones, ideas de nombres, adaptación de contenido de capacitación, borradores educativos.

## Consideraciones éticas
- Los cinco pilares (imparcialidad/equidad, robustez, explicabilidad, transparencia, privacidad) se aplican a cada forma de IA, con matices por contexto: préstamos, agricultura, arte público, contenido generado.
- Riesgos señalados: sesgo y discriminación, desinformación y deepfakes, violaciones de privacidad, uso indebido de datos, pérdida de confianza pública.
- Uso responsable: revisar resultados, dar crédito a las fuentes e indicar cuándo la IA generó el contenido.
- Nota de consistencia del material: en la lección 3 el pilar de explicabilidad se rotula "Justificabilidad" y la robustez aparece como "Solidez" en el resumen; en las lecciones 1 y 4 se usa "equidad" donde otras usan "imparcialidad". Se tratan como el mismo concepto.

## Preguntas de repaso
1. ¿En qué se diferencian la IA predictiva y la IA para la toma de decisiones?
   **R:** La predictiva estima lo que podría pasar sin decidir; la de decisión evalúa opciones y elige o recomienda la mejor según criterios definidos.
2. ¿Cuáles son los cinco pasos con que la visión artificial procesa una imagen?
   **R:** Captura, preprocesamiento, detección de características, reconocimiento de patrones y resultado de la decisión.
3. ¿Qué significa que la IA generativa sea multimodal? Da un ejemplo.
   **R:** Que trabaja con varios tipos de datos (texto, imagen, audio, video) en un mismo flujo; por ejemplo, de texto a imagen o de audio a texto.
4. ¿Cuándo conviene un motor de búsqueda y cuándo la IA generativa?
   **R:** El buscador, para una fuente directa, una cita o una actualización reciente; la IA generativa, para un punto de partida, un resumen o una respuesta creativa.
5. Enumera los cinco componentes de una instrucción eficaz.
   **R:** Rol, contexto, tarea, resultado (formato) y restricciones.
