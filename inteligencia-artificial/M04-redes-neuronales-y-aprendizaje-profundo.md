# Fundamentos de la IA: las bases para comprender la IA - M04 Redes neuronales y aprendizaje profundo

## Resumen
Las redes neuronales sustituyen las reglas "si... entonces" por sistemas en capas que aprenden patrones de los datos, de forma inspirada (no idéntica) en el cerebro: nodos como neuronas y pesos como sinapsis. Aprenden por ciclos de prueba y error. El aprendizaje profundo usa redes con muchas capas para extraer rasgos de forma automática, con ventajas claras pero también costos en datos, explicabilidad, sesgo y cómputo. La última lección trata la ética: fuentes de datos, impacto ambiental, imparcialidad, robustez frente a ataques y transparencia.

## Conceptos clave
- Reglas fijas "si... entonces" vs. aprendizaje a partir de datos.
- Red neuronal: capa de entrada, capas ocultas, capa de salida.
- Nodos, pesos y funciones de activación.
- Ciclo de aprendizaje de cuatro pasos.
- Aprendizaje profundo: tres ventajas, cuatro limitaciones, cuatro aplicaciones.
- Fuentes de datos: sitios web, redes sociales, sensores, libros y textos.
- Impacto ambiental y soluciones: IA más ecológica, selección eficiente de modelos, aprendizaje por transferencia.
- Ataques adversarios: hacking y envenenamiento; defensas.
- Transparencia en las fuentes de datos (cuatro pasos).

## Detalle por tema

### Lección 1: introducción a las redes neuronales
- **De reglas a aprendizaje:** las primeras computadoras eran deterministas (misma entrada, misma salida) y el programador debía prever cada caso. Ejemplo: un filtro de spam con la regla "FREE MONEY = spam" fallaba cuando los spammers escribían "FR33 M0N3Y", y obligaba a reescribir reglas sin parar. El machine learning aprende de miles de correos válidos y no deseados (exceso de mayúsculas, remitentes extraños). Aun así, los primeros sistemas de aprendizaje manejaban mal imágenes, voz y lenguaje; las redes neuronales cubrieron ese hueco.
- **Enfoque en capas:** ante una foto, la primera capa halla bordes, la siguiente forma figuras con ellos y las más profundas reconocen objetos completos. El aprendizaje profundo usa muchas capas (a veces cientos) y grandes volúmenes de datos; ejemplo: la traducción automática aprende leyendo millones de documentos en varios idiomas.
- **Estructura de una red neuronal:**
  - Capa de entrada: recibe números, palabras o imágenes y los convierte en valores numéricos (los píxeles de una foto).
  - Capas ocultas: combinan y transforman las entradas para detectar patrones (bordes, colores, formas).
  - Capa de salida: entrega el resultado, a menudo una puntuación de probabilidad o etiqueta (árbol, casa o automóvil).
- **Inspiración en el cerebro:**
  - Neuronas y nodos: una neurona solo envía señal si recibe suficientes entradas hasta su "punto de activación"; los nodos funcionan igual y filtran lo irrelevante (ejemplo del "7" escrito a mano).
  - Sinapsis y pesos: las conexiones cerebrales se fortalecen con la práctica; en la red, los pesos determinan la fuerza de las conexiones y se ajustan cuando mejora el desempeño (el detector de spam fortalece las conexiones que ayudan a identificarlo).
  - Diferencias: el cerebro aprende rápido con poca energía; la red necesita muchos ejemplos y mucha potencia.
- **Recorrido dentro de la red (video):** una directora creativa pide una imagen con una instrucción de texto. La capa de entrada convierte cada frase en datos numéricos; las capas ocultas, con millones de neuronas artificiales, activan patrones aprendidos (rostros, ropa, calles, luz); las funciones de activación destacan los rasgos importantes y apagan los demás; la capa de salida genera la imagen píxel por píxel como su mejor suposición según el entrenamiento.
- **Ciclo de prueba y error (cuatro pasos):**
  1. Hacer una estimación con su conocimiento actual (al inicio, muy inexacta).
  2. Evaluarla comparándola con la respuesta correcta.
  3. Aprender del error: medir cuán grande fue (errores grandes piden cambios grandes).
  4. Actualizar el cálculo interno para acertar mejor la próxima vez.
  El ciclo se repite miles o millones de veces.

### Lección 2: aprendizaje profundo
- **Definición y diferencia:** el machine learning tradicional exige que las personas elijan a mano las características; el aprendizaje profundo las extrae automáticamente aprendiendo rasgos simples y combinándolos en conceptos avanzados (líneas y bordes, luego ojos, luego rostros, luego personas concretas).
- **Ventajas:**
  - Aprende características automáticamente, sin guía manual.
  - Mejora al procesar más datos (los asistentes de voz mejoran con más acentos y dialectos).
  - Se adapta a distintos problemas (imágenes, lenguaje, estimaciones numéricas) ajustando la configuración existente.
- **Desafíos y limitaciones:**
  - Requiere grandes cantidades de datos de calidad; reunir y etiquetar es caro (ej. enfermedades raras con pocos registros).
  - Carece de explicaciones claras ("caja negra"): un banco no puede justificar rechazos de préstamos.
  - Amplifica sesgos de los datos de entrenamiento (contratación, préstamos, aplicación de la ley).
  - Consume muchos recursos computacionales y energía; puede quedar fuera del alcance de organizaciones pequeñas.
- **Aplicaciones:** traducción de idiomas, sistemas de recomendación, automóviles autónomos (cámaras y radares), diagnóstico médico (radiografías, análisis, síntomas).

### Lección 3: la ética del aprendizaje continuo
- **Fuente de datos:** lugar, sistema o medio original del que se recopila información para entrenar. Si proviene de un solo hospital o región, el modelo puede fallar con otras poblaciones.
  - Sitios web: texto, imágenes y datos de productos; dudas sobre el consentimiento de los creadores.
  - Redes sociales: publicaciones y datos de interacción para moderación, sentimiento y recomendación; pueden reflejar sesgos demográficos y perjudicar a grupos subrepresentados.
  - Datos de sensores: cámaras, micrófonos, GPS y monitores ambientales; dudas de privacidad y consentimiento.
  - Libros y textos: noticias, artículos de investigación; los textos históricos pueden incrustar sesgos en los sistemas actuales.
- **Impacto ambiental:** consumo de energía (servidores y GPU funcionando días o semanas) y huella de carbono (CO₂ cuando la electricidad viene de carbón o gas). El material cita comparaciones ilustrativas: entrenar un LLM puede consumir tanta energía como un hogar medio durante varios meses, y emitir tanto CO₂ como varios vuelos transatlánticos, según la fuente de energía.
- **Soluciones:**
  - Diseño y optimización de IA más ecológica: energías renovables en centros de datos, algoritmos más eficientes, modelos optimizados para conjuntos de datos más pequeños (ej. entrenar 50 % más rápido en un centro de datos solar).
  - Selección y uso eficientes de modelos: tamaño adecuado a la tarea, modelos preentrenados, aprendizaje por transferencia, ajuste fino de un modelo más pequeño (ej. reducir el consumo un 90 %).
- **Imparcialidad:** capacidad del modelo de producir resultados equitativos para personas y grupos, minimizando sesgos. La actividad práctica (rol de consultor en ética de IA) **no está cubierta**: su contenido interactivo no aparece en el material; solo se indica que el sesgo puede surgir en cualquier etapa del desarrollo y ser amplificado si no se diseña y supervisa con cuidado.
- **Robustez:** mantener un desempeño preciso ante datos nuevos, ruidosos o difíciles (reconocimiento de voz con ruido o acentos). Amenazas intencionales (ataques adversarios):
  - Ataques de hacking: durante el uso del modelo, con entradas diseñadas para causar errores (ruido imperceptible en una señal de alto que el vehículo lee como límite de velocidad).
  - Ataques de envenenamiento: durante el entrenamiento, con datos maliciosos (spam bien diseñado etiquetado como seguro); incluso pocos datos envenenados dañan la fiabilidad.
  - Defensas: entrenamiento adversarial (con ejemplos normales y manipulados), validación de entradas y monitoreo continuo.
- **Transparencia en las fuentes de datos:** apertura sobre diseño, datos de entrenamiento y proceso de decisión. Cuatro pasos:
  1. Encontrar la fuente: quién, cuándo y cómo recopiló los datos; transformaciones aplicadas.
  2. Verificar la calidad: exactitud, integridad, duplicados, valores atípicos, vigencia y posibles sesgos.
  3. Compartir la información: documentar fuentes, métodos, limitaciones y usos recomendados.
  4. Mejorar la selección de datos: aprender de lo anterior, fijar metas de calidad y monitorear.

## Intuición vs. formalismo
- **Red neuronal.** Intuición: una cadena de filtros que va de lo simple a lo complejo. Formal: sistema computacional de capas de unidades de procesamiento interconectadas que aprende a reconocer patrones y calcular a partir de grandes conjuntos de datos.
- **Peso.** Intuición: el "volumen" de cada conexión, que sube con la práctica. Formal: valor que determina la fuerza de la conexión entre partes de la red y se ajusta durante el aprendizaje.
- **Función de activación.** Intuición: el interruptor que decide qué señales pasan. Formal: función dentro de cada capa oculta que activa o desactiva señales para centrar la red en los datos más útiles.
- **Ciclo de prueba y error.** Intuición: tambalearse en la bici y corregir. Formal: repetición de estimar, evaluar, medir el error y actualizar los cálculos internos.
- **Aprendizaje profundo.** Intuición: aprender por niveles, de lo básico a lo avanzado. Formal: tipo de machine learning que usa redes neuronales artificiales de múltiples capas y aprende características simples para combinarlas en conceptos más avanzados.
- **Caja negra.** Intuición: se ve lo que entra y sale, no lo que ocurre dentro. Formal: modelo cuya forma de generar salidas es difícil de interpretar.
- **Fuente de datos.** Intuición: de dónde "bebe" el modelo. Formal: ubicación, sistema o medio original desde el que se recopila información para entrenar.
- **Robustez.** Intuición: que no se confunda con ruido o trucos. Formal: capacidad de mantener un desempeño preciso con datos nuevos, ruidosos o desafiantes.
- **Ataque adversario.** Intuición: engañar a la IA a propósito. Formal: intento deliberado de inducir errores, ya sea durante el uso (hacking) o el entrenamiento (envenenamiento).
- **Transparencia.** Intuición: mostrar cómo se hizo. Formal: grado de apertura de un modelo sobre su diseño, fuentes de datos de entrenamiento y proceso de decisión.

## Supuestos y limitaciones
- Las redes neuronales necesitan muchos ejemplos y energía; el cerebro es más eficiente.
- El aprendizaje profundo depende de datos abundantes, de buena calidad y representativos.
- No es la solución adecuada para todos los problemas (costo, falta de explicabilidad, sesgo).
- Los modelos aprenden de los datos tal cual: reproducen sus sesgos.
- Las cifras de energía y emisiones del material son comparaciones ilustrativas, no mediciones.

## Aplicaciones y ejemplos
- Generación de imágenes a partir de texto, reconocimiento de rostros y voz, mejora automática de fotos del teléfono.
- Traducción, recomendaciones, vehículos autónomos, diagnóstico médico.
- Filtros de spam que aprenden, evaluación de solicitantes, aprobación de préstamos.

## Consideraciones éticas
- Consentimiento y privacidad en datos de sitios web y sensores.
- Sesgo y subrepresentación en redes sociales y textos históricos.
- Huella ambiental y prácticas sostenibles.
- Seguridad frente a ataques adversarios.
- Documentación transparente de datos como base de confianza.

## Preguntas de repaso
1. ¿Qué limitación de las reglas "si... entonces" resuelve el machine learning?
   **R:** Que hay que prever cada situación a mano; el aprendizaje detecta los patrones por sí solo a partir de ejemplos.
2. Describe la función de las tres capas principales de una red neuronal.
   **R:** La de entrada convierte los datos en valores numéricos, las ocultas detectan patrones al combinarlos y la de salida entrega el resultado (etiqueta o probabilidad).
3. ¿Cuáles son los cuatro pasos del ciclo de prueba y error?
   **R:** Hacer una estimación, evaluarla frente a la respuesta correcta, aprender del error midiendo su tamaño y actualizar el cálculo.
4. ¿En qué se diferencia un ataque de hacking de uno de envenenamiento?
   **R:** El hacking apunta al modelo durante su uso con entradas manipuladas; el envenenamiento corrompe los datos de entrenamiento.
5. Menciona cuatro desafíos del aprendizaje profundo.
   **R:** Requiere grandes cantidades de datos, carece de explicaciones claras, amplifica sesgos existentes y consume muchos recursos computacionales.
