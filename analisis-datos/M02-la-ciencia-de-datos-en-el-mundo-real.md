# Data Fundamentals - M02 La ciencia de datos en el mundo real

## Resumen
La ciencia de datos es un enfoque multidisciplinario que combina método científico, estadística, programación, IA y narración para extraer información útil de los datos. Se apoya en metodologías repetibles; el módulo presenta tres clásicas (CRISP-DM, KDD, SEMMA) y desarrolla una de seis pasos, desde entender el negocio hasta implementar el modelo. Cierra con aplicaciones por industria y con los roles de un equipo de proyecto.

## Conceptos clave
- **Data science:** comprender el mundo mediante el análisis científico de datos digitales para obtener información accionable.
- **5 Whys:** técnica para llegar a la causa raíz preguntando "por qué" de forma encadenada.
- **Methodology:** estrategia general que guía un proceso, independiente de herramientas.
- **CRISP-DM, KDD, SEMMA:** metodologías clásicas de minería de datos, todas iterativas.
- **Descriptive statistics:** resumen numérico de un conjunto de datos.
- **Tokenization:** dividir texto en unidades (tokens) para convertirlo en números.
- **Data model / model training:** modelo que representa los datos y se entrena con machine learning para predecir.
- **Supervised, unsupervised y reinforcement learning:** tres formas de entrenar un modelo.
- **Model deployment:** integrar el modelo en el entorno de producción.
- **Roles:** data analyst, data scientist, data engineer (y data journalist).

## Detalle por tema

### Qué es la ciencia de datos
- Mezcla método científico, matemáticas y estadística, programación especializada, análisis avanzado, IA y narración.
- Su meta es extraer valor de los datos en cualquier forma, tratándolos como materia prima.
- Es un proceso científico repetible, aunque no por eso mecánico: deja espacio a la creatividad.
- Quien la practica prepara los datos, hace análisis avanzado, presenta patrones a los interesados y construye modelos para predecir resultados y orientar acciones futuras.
- Ciencia, tecnología y datos están vinculados: la formación científica permite plantear hipótesis, la tecnología permite clasificar datos y predecir, y los datos (estructurados y no estructurados, como video, blogs o tuits) aportan la información.

### Curiosidad y los 5 Whys
- La curiosidad es una de las cualidades más importantes del científico de datos; sus preguntas suelen empezar con "por qué".
- **5 Whys:** se pregunta "por qué", se toma la respuesta y se vuelve a preguntar, unas cinco veces; la última respuesta debería señalar la causa raíz.
- Si hay varias causas raíz, se repite el ejercicio con otra secuencia de preguntas.
- Cinco es una guía, no una regla fija. La técnica evita suposiciones y saltar a la respuesta obvia.

### Análisis de datos vs. ciencia de datos
| Rol | Qué hace con los datos |
|---|---|
| Data analyst | Recopila y examina grandes conjuntos para hallar tendencias, previsiones y visualizaciones que cuenten una historia y apoyen decisiones |
| Data scientist | Diseña procesos nuevos de modelado, usa algoritmos y análisis predictivo y estadístico, organiza datos no estructurados y crea sus propias metodologías de predicción |

Ambos buscan convertir el análisis en inteligencia de negocio; cambian las tácticas.

### Metodologías
- Una metodología es un marco general, no una tecnología ni un recetario de técnicas.
- CRISP-DM, KDD y SEMMA usan minería de datos, funcionan mejor con datos estructurados, sirven para análisis descriptivo y predictivo y comparten actividades como recopilar, transformar, modelar y evaluar. No son adecuadas para proyectos con datos no estructurados como imágenes o texto.

| Metodología | Pasos o fases | Notas |
|---|---|---|
| CRISP-DM (Cross-Industry Standard Process for Data Mining) | Comprensión del negocio, comprensión de los datos, preparación de los datos, modelado, evaluación, implementación | Impulsada por un programa europeo de investigación (ESPRIT); flexible, usable en cualquier industria; iterativa, con secuencia no estricta; destaca por empezar en el negocio; una de las más populares |
| KDD (Knowledge Discovery in Databases) | Selección, preprocesamiento, transformación, minería de datos, interpretación y evaluación | Iterativa, el conocimiento obtenido se reinyecta; sirve para entender clientes y anticipar compras; no contempla arquitectura de big data, ética ni roles de equipo |
| SEMMA | Sample, Explore, Modify, Model, Assess | Desarrollada por SAS Institute; centrada en la tarea de modelado; iterativa; útil en fraude, retención y rotación de clientes, marketing de bases de datos, fidelización, segmentación de mercado y análisis de riesgo |

### Metodología de seis pasos
Es independiente de herramientas, repetible y de pasos adaptables. Combina análisis descriptivo ("qué pasa") y diagnóstico ("por qué") para proponer una solución, y luego modelos con IA y análisis predictivo ("qué podría pasar") y prescriptivo ("qué debería pasar") para anticipar problemas.

**Paso 1. Comprensión del negocio**
- Todo proyecto comienza aquí, antes de explorar datos.
- El **business sponsor** (puesto de liderazgo) plantea el "punto débil", apoya el proyecto y participa todo el tiempo revisando resultados.
- El equipo usa **design thinking** (enfoque centrado en el usuario y la empatía) y puede hacer talleres para: definir el problema, fijar objetivos, crear personas que representen al usuario final y documentar requisitos de negocio.
- Con el problema claro, el data scientist define el **enfoque analítico**, traduciéndolo a técnicas estadísticas o de ML. Ejemplo: predecir si un cliente responde sí o no lleva a un modelo de regresión logística.

**Paso 2. Exploración y preparación de datos**
- Se recopilan datos estructurados y no estructurados de hojas de cálculo, bases de datos e Internet; si hay vacíos, se revisan requisitos y se recopila más.
- La exploración inicial busca patrones, relaciones y características prometedoras, y puede cambiar la hipótesis inicial.
- La preparación es el paso que más tiempo consume: construir el conjunto para modelar, limpiar, combinar fuentes y cubrir brechas.
- Los datos reales suelen venir incompletos o erróneos, dañados (líneas rotas, campos mal ubicados), demasiado aleatorios, irrelevantes, con valores atípicos que sesgan o con valores omitidos. Como revisarlos a mano no escala, se usan procesos automatizados.

**Paso 3. Representación y transformación de datos**
- Objetivos: entender los datos, evaluar su calidad y obtener primeras conclusiones.
- **Estadística descriptiva** (responde "qué ocurre"):
  - N: total de observaciones.
  - Mean: promedio.
  - Median: valor central de una lista ordenada.
  - Mode: valor más frecuente.
  - Mínimo y máximo.
  - Desviación estándar: dispersión respecto a la media.
- **Visualizaciones exploratorias:** la estadística sola puede engañar, así que se añaden diagramas, gráficos y mapas para ver distribuciones, patrones y tendencias.
- La calidad de entrada importa: datos malos producen un modelo de bajo rendimiento.
- **Transformación:** se estructura la información en un formato que el modelo de ML acepte. Los modelos solo entienden números, por eso el texto o las imágenes se convierten; por ejemplo, la **tokenización** parte el texto en tokens que luego se vuelven numéricos.
- Se normalizan los datos hacia "datos ordenados" (tidy data) en vez de desordenados, y puede ser necesario ajustar el enfoque analítico del paso 1.

**Paso 4. Visualización y presentación de datos**
- La visualización culmina el trabajo de transformación, permite probar hipótesis y suposiciones y debe contar una historia que responda al problema de negocio. Debe ser eficaz, atractiva e impactante.
- Tipos de gráfico y uso (mismos que en DF-M01): circular (proporción de pocos elementos, suma 100 %), barras (comparar y clasificar), columnas (verticales, admiten negativos), líneas (tendencias en el tiempo), dispersión (relación entre dos variables y atípicos).
- La presentación final debe ser clara para el sponsor. Se planifica según:
  - **Finalidad:** qué problema se aborda.
  - **Público:** quién la verá y qué le aporta.
  - **Datos:** si están bien representados y si habrá que actualizarlos.
  - **Contexto:** dónde vivirá (software, sitio web, informe).

**Paso 5. Entrenamiento de modelos de datos**
- Un **modelo de datos** identifica datos, atributos y relaciones, y ofrece una vista generalizada del escenario de negocio. Sirve para predecir mejor y entender el sistema modelado.
- Se experimenta con distintos tipos de modelo y se entrena con **machine learning**: la máquina aprende de los datos sin que se le programen reglas.

| Método | Cómo aprende | Ejemplo del material |
|---|---|---|
| Supervised | Con muchos ejemplos ya etiquetados; crea reglas generales para casos nuevos y mejora con mejores datos de entrenamiento | Imágenes etiquetadas "perro" para reconocer perros |
| Unsupervised | Con gran volumen de datos sin etiquetar; clasifica por sí sola | Fotos y artículos sobre perros para identificar uno nuevo |
| Reinforcement | Por ensayo y error, con recompensas y penalizaciones; sin objetivo específico | Vehículos autónomos, drones y robótica |

**Paso 6. Implementación de modelos**
- El modelo se integra en el entorno de producción con las herramientas elegidas por la empresa y sigue generando predicciones. Opera según un plan y el data scientist debe mantenerlo.

### Aplicaciones
Salud (detectar y predecir enfermedades, recomendaciones personalizadas), transporte (rutas de envío en tiempo real), deportes (rendimiento de atletas), gobierno (evasión fiscal, tasas de encarcelamiento), comercio electrónico (colocación automática de anuncios), videojuegos (mejores experiencias) y redes sociales (algoritmos de compatibilidad). Empresas como Amazon, Google y Facebook usan estos conceptos para decidir.

### Equipo de proyecto
- El resultado es tan bueno como el equipo que recopila, analiza e interpreta; todos deben entender el problema de negocio.
- Roles comparados: data analyst, data scientist y data engineer. Las organizaciones los nombran distinto y, según su tamaño, una persona puede reunir varios.
- **Data journalist:** rol no técnico centrado en comunicar, que convierte hechos en una historia con datos y visualizaciones.
- No cubierto: responsabilidades detalladas de cada rol (el texto solo los nombra) y el ejemplo de tabla de ingresos por nivel educativo del paso 3, que no aparece en el material.

## Interpretación de resultados
- Con estadística descriptiva, leer juntos el promedio, la mediana y la moda y la desviación estándar para ver el centro y la dispersión; una sola medida puede engañar.
- Complementar con gráficos exploratorios antes de modelar.
- Verificar la calidad de los datos de entrada: determina el desempeño del modelo.
- Al presentar, validar que el gráfico responda a la pregunta de negocio y que el sponsor lo pueda interpretar.

## Herramientas
- **Python:** transformación de datos, análisis detallado y visualizaciones más complejas.
- Procesos automatizados de preparación de datos y software de visualización (sin herramienta específica en el material).

## Preguntas de repaso
1. **¿Cómo se usa la técnica de los 5 Whys y qué busca?**
   Se pregunta "por qué", se toma la respuesta y se vuelve a preguntar, unas cinco veces, hasta llegar a la causa raíz; si hay varias causas se repite con otra secuencia.
2. **¿Qué distingue a un data scientist de un data analyst?**
   El analista examina conjuntos de datos para hallar tendencias y contar historias; el científico diseña procesos de modelado, usa algoritmos y análisis predictivo y crea sus propias metodologías de predicción.
3. **¿Qué fases tiene CRISP-DM y qué la hace particular?**
   Comprensión del negocio, de los datos, preparación, modelado, evaluación e implementación; destaca por partir del negocio y ser iterativa.
4. **¿Por qué es crítica la preparación de datos y qué problemas suelen presentar los datos reales?**
   Es el paso más largo y condiciona el modelo; los datos pueden ser incompletos, dañados, irrelevantes, con atípicos o con valores omitidos.
5. **Diferencia entre aprendizaje supervisado, no supervisado y reforzado.**
   El supervisado aprende de ejemplos etiquetados, el no supervisado de datos sin etiquetar, y el reforzado por ensayo y error con recompensas y penalizaciones.
