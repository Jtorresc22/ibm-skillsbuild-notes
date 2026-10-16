# Data Fundamentals - M01 Introducción a los conceptos de datos

## Resumen
Los datos son un activo clave y se generan en volúmenes crecientes. El módulo los clasifica (estructurados/no estructurados, cuantitativos/cualitativos), presenta big data y sus 5 V, y describe los cuatro tipos de análisis (descriptivo, diagnóstico, predictivo, prescriptivo). Después resume los pasos para analizar datos, con ETL como único paso detallado, y cierra con visualización y narración de datos.

## Conceptos clave
- **Structured / unstructured data:** con o sin formato en filas y columnas.
- **Quantitative (discrete, continuous) / qualitative (nominal, ordinal) data.**
- **Big data y las 5 V:** volume, variety, velocity, veracity, value.
- **Descriptive, diagnostic, predictive, prescriptive analytics:** qué pasa, por qué, qué pasará, qué hacer.
- **ETL (Extract, Transform, Load):** integración de datos de varias fuentes en un destino consistente.
- **Data visualization y data storytelling:** explorar y comunicar resultados.

## Detalle por tema

### Tipos de datos

#### Por qué importan los datos
- Las empresas recogen datos de clientes, hábitos de uso, tráfico web y demografía.
- Beneficios mencionados: mejorar operaciones, entender mejor al cliente, ganar eficiencia, reducir costos, aumentar ganancias e innovar.
- También se usan en ONG, gobiernos y universidades para problemas globales (pobreza, cambio climático, enfermedades, desigualdad).
- El analista sigue un proceso de recopilar, limpiar y transformar datos para responder "qué nos dicen los datos" y decidir mejor.

#### Volumen de datos
- Se estima que se crean unos 2,5 trillones de bytes al día (un trillón = 1 seguido de 18 ceros).
- Proyección: más de 180 zettabytes de datos creados globalmente hacia 2025 (un zettabyte = 1 seguido de 21 ceros).
- En 2020 hubo un récord de datos creados y replicados, por encima de lo previsto, por el aumento de trabajo, estudio y ocio desde casa durante la pandemia de COVID-19.
- Cifras de ejemplo del material: 3 mil millones de minutos de llamadas por Skype al día, 5 mil millones de fotos/videos en Snapchat al día, 333,2 mil millones de correos al día.

#### Datos estructurados vs. no estructurados
| Aspecto | Estructurados | No estructurados |
|---|---|---|
| Organización | Filas y columnas, agrupables por características | Sin formato ni estructura incorporada |
| Ejemplos | Nombres, fechas, direcciones, números de tarjeta, datos bursátiles, geolocalización | Imágenes, texto, publicaciones en redes, comentarios de clientes, registros médicos, letras de canciones |
| Dificultad | Más fáciles de manipular | Más difíciles de procesar |
| Valor | Los más útiles por su orden | Suelen revelar lo que se desconoce |

- Ejemplo combinado: las fotos de licencias de conducir son no estructuradas; la tabla con nombre, dirección y número de licencia que las indexa es estructurada. Igual con libros: el texto es no estructurado, el catálogo (título, autor, fecha) es estructurado.
- Ejemplo de uso: una empresa de software recibe correos con reportes de errores. Analizando el texto (por ejemplo, su sentimiento) y convirtiendo parte en datos estructurados, el analista detecta patrones y localiza el problema.
- Proporción aproximada mundial: 80 % no estructurados, 20 % estructurados.

#### Bases de datos
- Una base de datos mantiene los datos ordenados para consultarlos con software de consulta y cálculo.
- Convertir los datos a un formato estándar ("datos ordenados") simplifica almacenarlos y analizarlos.
- En una base relacional, las tablas se vinculan por datos comunes. Ejemplo: una tabla de personas y direcciones y otra de propiedades y propietarios se enlazan por los propietarios que aparecen en ambas.

#### Cuantitativos vs. cualitativos
- **Cuantitativo** (piensa en "cantidad"): altura, peso, longitud, presión arterial, temperatura.
- **Cualitativo** (piensa en "calidad"): olor, ubicación, color, textura, estado civil.

#### Subtipos
| Tipo | Subtipo | Idea | Ejemplos |
|---|---|---|---|
| Cuantitativo | Discreto | Valores enteros indivisibles, solo se cuentan unidades completas | Habitaciones de una casa, personas en un cine |
| Cuantitativo | Continuo | Puede tomar infinitos valores y dividirse en decimales; puede variar en el tiempo | Peso de un auto, altura, velocidad de un avión, temperatura de una sala |
| Cualitativo | Nominal | Etiqueta sin orden ni jerarquía | Color de cabello, religión, estado civil, etnia |
| Cualitativo | Ordinal | Categorías con orden según su posición en una escala | Notas A/B/C, tallas S/M/L, niveles de satisfacción; se usa para medir percepciones y opiniones |
### Big data

#### Definiciones (no hay una universal)
- **Bernard Marr:** todo lo que hacemos deja un rastro digital que podemos analizar para decidir mejor; lo impulsan el mayor acceso a datos y la mejor tecnología para extraer información de ellos.
- **Oracle:** conjuntos más grandes y complejos, sobre todo de fuentes nuevas, demasiado voluminosos para el software tradicional, pero capaces de resolver problemas de negocio antes inabordables.
- **Gartner:** activos de información de alto volumen, velocidad y/o variedad que requieren procesamiento innovador y rentable para mejorar la comprensión, las decisiones y la automatización.

#### Las 5 V
| V | Pregunta que responde | Puntos del material |
|---|---|---|
| Volumen | ¿Cuántos datos hay que procesar? | Escalas de exabytes, zettabytes y yottabytes; casi 8 mil millones de personas (2022) con dispositivos que generan datos; se requieren herramientas y almacenamiento adecuados |
| Variedad | ¿Son estructurados o no estructurados? | Hojas de cálculo y bases de datos, pero también informes, correos, publicaciones, audio, blogs, registros médicos e investigaciones de mercado; exige distintas herramientas y técnicas |
| Velocidad | ¿Con qué rapidez se generan y mueven? | Flujo continuo; ejemplo de Facebook por minuto: 510 000 comentarios, 293 000 estados y 240 000 fotos; existen tecnologías de transmisión en tiempo real o casi real, locales y en la nube |
| Veracidad | ¿Qué tan exactos y confiables son? | Revisar origen, integridad y trazabilidad; en big data la calidad es menos controlable (ejemplo: un tweet con hashtags, abreviaturas, errores y coloquialismos); requiere presupuesto y métodos de limpieza |
| Valor | ¿Se puede extraer provecho? | No es solo ganancia: también beneficios médicos, sociales o de satisfacción de clientes y empleados; hay que definir el valor buscado y filtrar el "ruido" |

#### Unidades de volumen citadas
- 1 gigabyte, aproximadamente mil millones de bytes.
- 1 exabyte, mil millones de gigabytes.
- 1 zettabyte, aproximadamente mil exabytes.
- 1 yottabyte, mil zettabytes.

#### Velocidad: matiz
Las empresas necesitan conocer el tiempo transcurrido entre que se toma una muestra y que se usa, porque ese plazo puede cambiar.
### Tipos de análisis de datos

| Tipo | Pregunta | Qué hace | Ejemplos del material |
|---|---|---|---|
| Descriptivo | ¿Qué está pasando? | Foto de tendencias y patrones con datos históricos y actuales; señala si algo va bien o mal, sin explicar la causa; ayuda a decidir dónde investigar | Número de suscriptores, encuestas de satisfacción, ingresos mensuales, reportes diarios de bolsa, perfil demográfico de clientes (30 % autónomos) |
| Diagnóstico | ¿Por qué ocurre? | Profundiza en lo descriptivo para hallar causas, conectar datos e identificar patrones de comportamiento | Causa de envíos lentos en una región; relación entre diagnósticos y medicamentos recetados; pocos servidores que causan la mayoría de las caídas |
| Predictivo | ¿Qué es probable que pase? | Usa datos históricos y modelos predictivos para estimar la probabilidad de un evento, una cantidad o un momento; a menudo recurre a machine learning y deep learning | Segmentación de clientes para oportunidades de venta; tasa de fallas de una pieza de auto; predicción del clima en otras zonas |
| Prescriptivo | ¿Qué debería ocurrir? | Combina lo anterior para decidir el curso de acción: evitar un problema futuro o aprovechar una tendencia; suele aplicarse a un conjunto de acciones, con alto compromiso de recursos; usa machine learning, reglas de negocio y algoritmos | App de tráfico que elige ruta según distancia, velocidad y congestión; calendario de exámenes que detecta choques de horario; sistemas de IA de Facebook, TikTok y Netflix |

#### Relación entre tipos
- Están conectados y dependen unos de otros en cierta medida.
- Pasar de descriptivo a predictivo y prescriptivo exige más capacidad técnica, pero da más información a la organización.
### Pasos para analizar datos

#### Antes de empezar
- Fijar un objetivo de negocio y un problema claro: qué preguntas se quieren responder.
- Según el material, buena parte del análisis (cerca del 90 %) consiste en plantear bien las preguntas.
- Definir las métricas de rendimiento: qué se mide y cómo.
- Cada empresa tiene su propio equipo, procesos y herramientas.

#### Pasos típicos (resumen del material)
1. Recopilar
2. Limpiar
3. Analizar
4. Visualizar

Detalle de cada paso: no cubierto en el material (solo aparece el listado y, aparte, ETL).

#### ETL
- Combina datos de múltiples fuentes en un almacén único y consistente, cargado en un data warehouse u otro sistema destino.
- Surgió en la década de 1970, con el auge de las bases de datos, y llegó a ser el método principal para procesar datos en proyectos de almacenamiento.
- Es la base de los flujos de análisis y de machine learning.
- Usos habituales:
  - extraer datos de sistemas heredados (legacy);
  - limpiar para mejorar calidad y consistencia;
  - cargar en una base de datos de destino.
### Visualización de datos

#### Para qué se visualiza
- Explorar e interpretar datos durante el análisis, para detectar patrones o tendencias.
- Comunicar resultados para que otros entiendan y decidan.
- Un solo gráfico puede responder muchas preguntas y simplifica temas complejos.

#### Data storytelling
- Tres ingredientes: datos, visualizaciones y narrativa.
- La narrativa explica qué ocurre y por qué importa; las visualizaciones revelan patrones difíciles de ver en filas y columnas; juntas pueden influir y mover a la acción.
- Objetivo: enlazar los resultados con quienes toman decisiones.

#### Tipos de comparación
| Comparación | Definición | Ejemplo |
|---|---|---|
| Proporción relativa | Parte que un subconjunto representa del total | En una clase de 25, 15 niñas = 3/5 y 10 niños = 2/5 |
| Categoría | Relación de orden (mayor, menor, igual) entre elementos | Ranking de jugadores por puntaje máximo |
| Tiempo | Datos secuenciados cronológicamente | Hora diaria de marea alta y baja |
| Frecuencia | Cuántas veces ocurre un evento | Nevó dos veces hoy: frecuencia 2 |
| Correlación | Relación (normalmente lineal) entre dos variables | Altura de padres e hijos |

#### Tipos de gráfico
| Gráfico | Útil para | Ejemplo del material |
|---|---|---|
| Circular (pie) | Proporción relativa de pocos elementos; las partes suman 100 % | Porcentaje de ganancias por sucursal de un supermercado |
| De barras | Comparar y clasificar muchas categorías; antes/después; cambio en el tiempo | Tráfico web mensual de una farmacia en línea durante un año |
| De columnas | Proporciones, datos en el tiempo, frecuencia; muestra datos negativos | Accidentes mensuales en almacenes frente al promedio |
| De líneas | Datos continuos en el tiempo, pequeños cambios, tendencias | Chats y correos respondidos al mes por un servicio de asistencia |
| De dispersión (scatter) | Relación entre dos conjuntos de datos, gran cantidad de puntos, valores atípicos | Satisfacción del cliente más alta con menor tiempo de respuesta en llamadas bancarias |

No cubierto: la imagen del material que asocia cada gráfico con datos cuantitativos o cualitativos no está en el texto recibido.

## Herramientas
- **Hojas de cálculo** (Google Sheets, Microsoft Excel): para datos estructurados en filas y columnas.
- **SQL (Structured Query Language):** para ordenar y consultar grandes volúmenes de datos repartidos en varias tablas conectadas.

## Interpretación de resultados
- En un gráfico circular, la suma de las secciones debe dar 100 %; sirve para ver de un vistazo qué categoría pesa más.
- En un gráfico de líneas, buscar tendencias y cambios pequeños a lo largo del tiempo.
- En un gráfico de dispersión, buscar patrones entre dos variables y puntos atípicos.
- Precaución: los métodos de visualización pueden presentar el mismo conjunto de datos de forma favorable o desfavorable al manipular variables; el problema no son los datos sino cómo se muestran.

## Preguntas de repaso
1. **¿Qué diferencia a los datos discretos de los continuos? Da un ejemplo de cada uno.**
   Los discretos son enteros indivisibles que se cuentan (personas en un cine); los continuos admiten infinitos valores y decimales (peso de un auto).
2. **Nombra las 5 V de big data.**
   Volumen, variedad, velocidad, veracidad y valor.
3. **Un grupo de servidores causa la mayoría de las caídas y una empresa investiga por qué. ¿Qué tipo de análisis es?**
   Diagnóstico: busca las causas de lo que muestra el análisis descriptivo.
4. **¿Qué es ETL y para qué se usa?**
   Extract, Transform, Load: integra datos de varias fuentes en un almacén consistente, por ejemplo para extraer de sistemas heredados, limpiar y cargar en una base de datos destino.
5. **¿Qué tres elementos combina el data storytelling y qué gráfico sirve para relacionar dos variables y ver valores atípicos?**
   Datos, visualizaciones y narrativa; el gráfico de dispersión.
