# Fundamentos de la IA: las bases para comprender la IA - M03 Machine Learning

## Resumen
El machine learning es el subconjunto de la IA que permite a las computadoras aprender de la experiencia y mejorar con más datos. Se presentan cinco tipos de aprendizaje (supervisado, no supervisado, semisupervisado, autosupervisado y por refuerzo), los modelos clásicos (árbol de decisión, regresión lineal y logística) y su relación con las redes neuronales. El módulo cierra con las alucinaciones de la IA generativa: por qué ocurren, cómo reducirlas y qué pilares de confianza aplican.

## Conceptos clave
- Machine learning y los cinco tipos de aprendizaje.
- Etiquetas, clasificación, regresión, puntuación de confianza.
- Agrupación en clústeres y detección de anomalías.
- Señal de supervisión, tarea de pretexto, aprendizaje contrastivo.
- Aprendizaje por refuerzo: agente, entorno, acciones, recompensas, política.
- Machine learning clásico: árbol de decisión, regresión lineal (simple y múltiple), regresión logística.
- Red neuronal y pseudoetiquetas.
- Alucinación y estrategias de mitigación: ajuste de modelos, feedback con intervención humana, calidad de datos, verificación posterior a la generación.

## Detalle por tema

### Lección 1: cómo aprenden las máquinas
- **Machine learning:** subconjunto de la IA con el que las computadoras aprenden de los datos y mejoran su rendimiento sin programación explícita para cada caso.
- **Aprendizaje supervisado:** el modelo entrena con ejemplos que traen la respuesta correcta (etiqueta) y luego ofrece resultados para datos nuevos.
  - Clasificación: asigna una categoría de un conjunto (auto o autobús, spam o no spam, lectura de escritura a mano).
  - Regresión: estima un valor numérico (precio de una casa, temperatura, calificación).
  - Puntuación de confianza: valor numérico con el que el modelo indica su certeza (p. ej. 85 % de que la foto es un perro); el modelo nunca responde con certeza absoluta.
  - Flujo (video): imágenes sin etiqueta no sirven; se etiquetan, el modelo detecta rasgos (forma, ruedas, ventanas), construye un modelo y clasifica una imagen nueva con cierta confianza.
- **Aprendizaje no supervisado:** el modelo busca patrones en datos sin etiquetas ni guía. Más difícil porque debe estructurar los datos antes de recomendar.
  - Agrupación en clústeres: agrupa puntos similares por sus características (segmentar compradores y dirigir anuncios).
  - Detección de anomalías: encuentra valores que se salen del patrón (cargos inusuales en una tarjeta).
  - Video: con imágenes de perros sin etiqueta, la IA agrupó por forma de oreja (3 grupos), luego por color de pelaje (3 grupos) y combinando rasgos obtuvo 5 clústeres que corresponden a razas.
- **Aprendizaje semisupervisado:** pocos datos etiquetados más muchos sin etiquetar; útil cuando etiquetar todo es caro o lento. Usa umbrales de confianza: solo incorpora los ejemplos de los que está más seguro (ej. una imagen médica etiquetada guía la interpretación de otras cuatro).
- **Aprendizaje autosupervisado:** el sistema crea sus propias tareas con partes de sus datos, sin etiquetas manuales; común en modelos de lenguaje y visión.
  - Señal de supervisión: resultado o etiqueta correcta durante el entrenamiento que guía la relación entre entradas y resultados; aquí se genera a partir de los propios datos.
  - Tareas de pretexto: pequeños retos que el modelo se plantea (predecir una palabra faltante, reconstruir parte de una imagen) para formar representaciones internas útiles.
  - Aprendizaje contrastivo: aprende comparando qué es similar y qué distinto (dos fotos del mismo objeto desde ángulos distintos).
- **Aprendizaje por refuerzo:** aprende probando acciones y recibiendo recompensas o penalizaciones (robótica, juegos, decisiones automatizadas). Componentes:
  - Agente: quien decide y actúa.
  - Entorno: el mundo en el que opera (un laberinto, una cocina).
  - Acciones: decisiones con las que interactúa (izquierda, derecha...).
  - Recompensas: señales tras cada elección sobre si fue útil.
  - Política: estrategia o reglas para elegir la siguiente acción; mejora con el tiempo.
  - Estado (mencionado en el video): feedback tras cada acción, que incluye posición actual y recompensas.
  - Video: un robot de cocina busca jugo de naranja; al inicio explora al azar, tras muchos episodios descubre atajos y aprende la ruta más corta.
- La calidad de los datos, el tipo de feedback y la evaluación son determinantes para una IA confiable.

### Lección 2: modelos clásicos de machine learning
- **Clásico vs. IA moderna:** el machine learning clásico usa cálculos matemáticos sobre datos estructurados con modelos simples y fáciles de entender; la IA moderna usa redes neuronales con muchas capas y rinde mejor con datos no estructurados (rostros, voz, traducción), pero exige más datos y cómputo.
- **Cuándo conviene el clásico:**
  - Datos pequeños (ej. algunos años de calificaciones).
  - Entrenamiento rápido (segundos o minutos, frente a horas o días del aprendizaje profundo).
  - Equipo básico (una laptop basta).
  - Se necesita explicar la decisión (ej. árbol de decisión en salud).
- **Árbol de decisión:** divide los datos en nodos mediante preguntas de sí o no hasta llegar a una decisión.
  - Nodo raíz: primera pregunta que divide los datos (¿hay oleaje?).
  - Nodos internos: conectan partes del árbol según la respuesta.
  - Nodo hoja: resultado final (surfear o no surfear).
- **Regresión lineal:** ajusta una línea recta a los datos para estimar un resultado continuo (cualquier número dentro de un rango).
  - Simple: una entrada y un resultado (minutos de entrenamiento diario vs. tiempo de carrera).
  - Múltiple: varias entradas para un resultado (asistencia, tareas y pruebas para estimar la nota final).
  - Ejemplo: más publicidad se asocia con más ventas; el modelo puede sugerir cuánta publicidad hace falta para una meta.
- **Regresión logística:** estima uno de dos resultados posibles a partir de variables de entrada; entrega una probabilidad, no un sí/no directo (70 % de que se pague un préstamo).
  - Posibilidad (odds): compara la oportunidad de que algo ocurra con la de que no (8 de 10 responden: odds 8 a 2).
  - Probabilidad: número entre 0 y 1 (8/10 = 0,8 = 80 %).
  - Función logística (sigmoide): convierte las odds en probabilidad con una curva en S; el modelo es más confiable en los extremos que en el centro.
  - Umbral: punto de corte para pasar de probabilidad a decisión binaria; típicamente 0,5. Bajarlo da más respuestas "sí" pero más errores; subirlo vuelve al modelo más estricto (ej. umbral 0,6 para decidir a quién ofrecer una promoción).
- **Diferencias:** el árbol usa preguntas paso a paso; la regresión logística usa una curva; la lineal predice valores (precio, tiempo), mientras que la logística predice la probabilidad de un resultado.

### Lección 3: machine learning, redes neuronales e IA
- **Red neuronal:** sistema de capas de unidades interconectadas (nodos) que identifica patrones y recomienda o decide; inspirada en la comunicación entre neuronas.
- **Tipos de aprendizaje en redes neuronales:**
  - Supervisado: ajusta sus respuestas a las etiquetas (ej. neumonía en radiografías).
  - No supervisado: capas sucesivas extraen rasgos sin etiquetas (agrupar galaxias por forma, brillo o color).
  - Semisupervisado: genera pseudoetiquetas (suposiciones confiables) para los datos sin etiquetar y sigue entrenando (ej. 500 secuencias de ADN etiquetadas frente a cientos de miles sin etiqueta).
  - Autosupervisado: crea sus propias tareas; capas iniciales detectan bordes o fragmentos de palabras, capas profundas combinan en objetos o significados (los LLM aprenden prediciendo palabras faltantes).
  - Por refuerzo: la red actúa como agente y ajusta su política según recompensas (robot que aprende a caminar).
- **Efecto del tipo de aprendizaje en los resultados:**
  - Resultados estructurados (formato uniforme): favorecidos por supervisado y semisupervisado.
  - Creatividad: favorecida por no supervisado (relaciones ocultas) y autosupervisado (modelo profundo de contexto y significado).
  - Mejora con el tiempo: por refuerzo (ciclo de feedback) y supervisado (más ejemplos etiquetados).

### Lección 4: cómo el machine learning ayuda a mejorar la IA
- **Alucinación:** resultado fabricado o incorrecto que el modelo presenta como verdadero (también contenido fuera de tema o repetitivo). Ocurre porque el modelo predice las palabras siguientes según patrones, no verifica hechos; prioriza lo plausible sobre lo exacto. Ejemplo del video: una analista recibe una cita de un estudio y una autora que no existen, y otra noticia inventada sobre una adquisición.
- **Riesgos:** decisiones basadas en información falsa, pérdida de credibilidad, presupuestos asignados a eventos imaginarios, hojas de ruta con funciones imposibles, rechazo indebido de prestatarios, riesgo para pacientes.
- **Estrategias para mejorar la exactitud:**
  - Ajuste de modelos: reentrenar con datos específicos del dominio (resumir notas de pacientes con terminología médica).
  - Feedback con intervención humana: personas revisan y corrigen mientras se genera el resultado.
  - Mejora de la calidad de los datos: datos limpios, precisos y relevantes (depurar la base de productos antes de entrenar).
  - Verificación posterior a la generación: comprobar el resultado final contra fuentes confiables antes de usarlo.
- **Hábitos del usuario:** cotejar citas y estadísticas con bases confiables, verificar plausibilidad, comparar modelos y preguntarse "¿tiene sentido?" y "¿puedo verificarlo?".

## Intuición vs. formalismo
- **Machine learning.** Intuición: la máquina mejora con la práctica en lugar de recibir reglas. Formal: subconjunto de la IA que permite a los sistemas aprender de los datos y mejorar su rendimiento con la experiencia.
- **Aprendizaje supervisado.** Intuición: estudiar con respuestas a la vista. Formal: entrenamiento con ejemplos etiquetados para hacer predicciones o recomendaciones sobre datos nuevos.
- **Aprendizaje no supervisado.** Intuición: ordenar fotos por parecido sin que te digan categorías. Formal: modelo que analiza datos sin etiquetas ni guía y busca patrones o agrupaciones por sí mismo.
- **Aprendizaje semisupervisado.** Intuición: unas pocas pistas bien señaladas y el resto por deducción. Formal: entrena con una pequeña cantidad de datos etiquetados más una cantidad mayor sin etiquetar.
- **Aprendizaje autosupervisado.** Intuición: tapar parte del texto y adivinar lo que falta. Formal: el sistema usa partes de sus propios datos para crear tareas y aprender sin ejemplos etiquetados.
- **Aprendizaje por refuerzo.** Intuición: prueba y error con premios y castigos. Formal: el modelo aprende a decidir probando acciones y recibiendo feedback como recompensas o penalizaciones.
- **Puntuación de confianza.** Intuición: "estoy 85 % seguro". Formal: valor numérico que indica el nivel de certeza del modelo sobre su resultado.
- **Árbol de decisión.** Intuición: juego de preguntas sí/no. Formal: modelo clásico que divide los datos en nodos para llegar a decisiones o clasificaciones.
- **Regresión lineal.** Intuición: la recta que mejor sigue los puntos. Formal: modelo que recomienda resultados continuos ajustando una línea recta a los datos.
- **Regresión logística.** Intuición: "¿qué tan probable es el sí?". Formal: modelo que estima uno de dos resultados posibles a partir de variables de entrada, mediante una probabilidad entre 0 y 1.
- **Alucinación.** Intuición: la IA inventa con seguridad. Formal: respuesta de un modelo fundacional con contenido fuera de tema, repetitivo, incorrecto o fabricado.

## Supuestos y limitaciones
- Supervisado: requiere datos etiquetados; nunca da certeza absoluta.
- No supervisado: más difícil, no recomienda hasta estructurar los datos.
- Semisupervisado: usa umbrales de confianza para no incorporar errores.
- Clásico: mejor con datos estructurados y tareas simples; la IA moderna maneja mejor datos no estructurados pero necesita más datos y cómputo.
- Regresión lineal: describe relaciones en línea recta; los casos reales suelen requerir varias variables.
- Regresión logística: el resultado depende del umbral elegido.
- Generación: las alucinaciones surgen cuando el modelo no tiene suficientes textos relacionados para producir detalles correctos.

## Aplicaciones y ejemplos
- Spam, reconocimiento facial, escritura a mano, estimación de precios.
- Segmentación de clientes, detección de fraude, imágenes médicas con pocas etiquetas.
- Robótica y videojuegos con refuerzo; modelos de lenguaje con autosupervisión.
- Modelo de pago de préstamos (logística), ventas según publicidad (lineal), diagnóstico explicable (árbol).

## Consideraciones éticas
- Las alucinaciones pueden causar rechazos indebidos de crédito o riesgos para pacientes.
- Explicabilidad: los LLM no extraen datos de fuentes fijas, por lo que es difícil rastrear por qué respondieron algo; se mitiga con diseño de instrucciones y citas.
- Equidad: los modelos aprenden sesgos de los datos; se audita el entrenamiento, se prueban resultados, se aplican filtros y se reentrena (caso de un revisor de currículums que favorecía a una universidad).
- Transparencia: informar limitaciones y datos de entrenamiento, y ofrecer citas, para saber cuándo verificar.

## Preguntas de repaso
1. ¿Qué diferencia hay entre clasificación y regresión?
   **R:** La clasificación asigna una etiqueta de un conjunto de categorías (auto o autobús); la regresión estima un valor numérico (precio de una casa).
2. ¿Qué es una tarea de pretexto en el aprendizaje autosupervisado?
   **R:** Un pequeño reto creado a partir de los propios datos (predecir una palabra faltante) que no es el objetivo final, pero ayuda al modelo a construir representaciones internas útiles.
3. Nombra los componentes del aprendizaje por refuerzo.
   **R:** Agente, entorno, acciones, recompensas y política (y el estado como feedback tras cada acción).
4. ¿Cómo convierte la regresión logística una probabilidad en una decisión?
   **R:** Con un umbral, normalmente 0,5: por encima responde sí y por debajo no; ajustarlo cambia la sensibilidad del modelo.
5. Menciona cuatro estrategias para mejorar la exactitud de la IA generativa.
   **R:** Ajuste de modelos con datos del dominio, feedback con intervención humana, mejora de la calidad de los datos y verificación posterior a la generación.
