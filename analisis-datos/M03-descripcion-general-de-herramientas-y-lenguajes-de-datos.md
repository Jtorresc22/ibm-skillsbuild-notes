# Data Fundamentals - M03 Descripción general de herramientas y lenguajes de datos

## Resumen
El módulo explica qué es el software de código abierto y cómo se colabora en él con Git y GitHub. Después recorre las herramientas habituales para analizar y visualizar datos (Excel, Google Sheets, SQL, Python, IBM Watson Studio, Tableau, Matplotlib) y otras tecnologías del ecosistema. Cierra con criterios para elegir herramientas según el proyecto: no existe una herramienta perfecta, solo la adecuada para un objetivo y una persona.

## Conceptos clave
- **Open source software:** software cuyo código es público y que una comunidad puede usar, ver, modificar y compartir bajo una licencia.
- **Git / GitHub:** control de versiones local y servicio en línea para alojar y colaborar en repositorios.
- **SQL / NoSQL:** SQL consulta datos estructurados en bases relacionales; NoSQL maneja datos no estructurados en bases no relacionales.
- **Python:** lenguaje gratuito de propósito general, muy usado en ciencia de datos.
- **Data Refinery:** herramienta de IBM Watson Studio para preparar y transformar datos.
- **Tableau y Matplotlib:** herramienta interactiva y biblioteca de Python para visualizar datos.
- **Selección de herramientas:** depende del tipo y volumen de datos, de los procesos, de las visualizaciones, del perfil de usuarios y del presupuesto.

## Detalle por tema

### Código abierto
- Cuatro aspectos: se puede **usar** para cualquier propósito (bajo licencia), **ver** el código, **modificar** (mejoras y correcciones vienen de cualquiera) y **compartir** contribuciones con un propósito común.
- Vocabulario:
  - **Comunidad:** quienes se relacionan con el proyecto y obtienen beneficio de él.
  - **Colaborador (contributor):** quien aporta al proyecto.
  - **Committer:** quien revisa y aprueba cambios y tiene permiso de escritura en el repositorio.
  - **Código de conducta:** pautas de comportamiento aceptable; todo proyecto debería tenerlo.
  - **Pautas de contribución:** reglas para participar en el proyecto.
- Ideas erróneas frecuentes:
  - Es gratis en cuanto a costo inicial (usar, modificar, distribuir), pero rara vez incluye soporte o garantía, y pueden surgir gastos de capacitación y mantenimiento.
  - Poder ver el código no lo hace abierto: los creadores deben conceder permiso para verlo y modificarlo.
  - Cada proyecto tiene su propia licencia con términos distintos; que se pueda descargar sin pagar no basta para ser de código abierto.
- Valor para el profesional de datos: aprender software nuevo, encontrar mentoría, mostrar experiencia y avanzar en la carrera.
- Valor para la empresa: más innovación gracias a código ya disponible, ahorro en desarrollo, documentación, pruebas y corrección de errores, influencia sobre la dirección tecnológica y mayor seguridad y fiabilidad.

### Git y GitHub
| | Git | GitHub |
|---|---|---|
| Qué es | Sistema de control de versiones de código abierto | Servicio en línea, no un software |
| Dónde | Se instala en la computadora | En la web, con cuentas gratuitas, profesionales y empresariales |
| Para qué | Seguir cambios en el código y coordinar a los programadores | Alojar código y colaborar desde cualquier lugar |

- Git se puede usar sin GitHub, pero GitHub requiere Git.
- Un **repositorio** funciona como la carpeta de un proyecto; puede ser público o privado y contener código, imágenes, video, hojas de cálculo y conjuntos de datos, con historial de revisiones.
- En GitHub se puede alojar un proyecto propio (crear repositorio y subir archivos) o contribuir a uno público existente (copiar el repositorio, hacer cambios y pedir revisión).

### Herramientas para analizar y visualizar
| Herramienta | Qué es | Puntos del material |
|---|---|---|
| Microsoft Excel | Hoja de cálculo de Microsoft | Ingresar, limpiar y examinar datos en filas y columnas; filtros, fórmulas y tablas dinámicas; gráficos circulares, de barras, de líneas y de dispersión, plantillas y recomendaciones, y combinación de tipos; limitación: gráficos sobre todo bidimensionales (eje X y eje Y), lo que dificulta mostrar varias variables a la vez |
| Hojas de cálculo de Google | Hoja de cálculo gratuita en línea | Ingreso, análisis y visualización para decidir con datos; varias personas editan a la vez; muchas empresas prefieren Excel por sus funciones estadísticas y analíticas |
| SQL | Lenguaje estándar para consultar bases de datos relacionales | Estándar ANSI desde 1986 e ISO desde 1987; es un lenguaje de consulta, no de programación; comandos como Select, Insert, Update, Delete, Create y Drop |
| NoSQL ("no solo SQL") | Acceso a bases no relacionales con datos no estructurados | Útil para big data y aplicaciones web en tiempo real (ejemplo: una red social que reúne terabytes diarios); tipos: de documentos, de columnas anchas y de grafos |
| Python | Lenguaje gratuito, de código abierto y propósito general | Creado por Guido van Rossum, lanzado en 1991; legible y de sintaxis parecida al inglés, menos líneas de código que otros lenguajes; conecta con bases de datos, lee y modifica archivos, maneja big data y cálculos complejos; con la biblioteca pandas permite analizar datos y visualizarlos |
| IBM Watson Studio | IDE colaborativo de ciencia de datos y machine learning | Trabaja con herramientas de código abierto; interfaz gráfica sin necesidad de programar; incluye Data Refinery |
| Tableau | Software de visualización e inteligencia empresarial | Analiza grandes volúmenes; crea paneles, gráficos, tablas, mapas e historias; interfaz intuitiva sin programar; visualizaciones interactivas |
| Matplotlib | Biblioteca de Python para gráficos 2D | Presentada por John Hunter en 2002; proyecto comunitario de código abierto; pocas líneas generan un gráfico; dispersión, histogramas, barras y más; visualizaciones estáticas, animadas o interactivas; exporta a varios formatos |

Capacidades de SQL: ejecutar consultas, recuperar, insertar, actualizar y eliminar registros; crear bases de datos, tablas, procedimientos almacenados y vistas; y definir permisos sobre tablas, procedimientos y vistas.

**Data Refinery (IBM Watson Studio):** convierte grandes cantidades de datos crudos en datos de alta calidad, muestra gráficos integrados para ver la distribución y permite programar trabajos para obtener resultados repetibles.

### Otras tecnologías
| Tecnología | Descripción |
|---|---|
| Apache Spark | Motor de análisis multilenguaje de código abierto para ingeniería de datos, ciencia de datos y ML, en un nodo o en clústeres; apto para conjuntos muy grandes |
| Jupyter Notebook | Aplicación web de código abierto con cuadernos que mezclan código interactivo, visualizaciones, ecuaciones y texto; permite colaborar y experimentar rápido |
| R y RStudio | R es un lenguaje gratuito para gráficos y estadística, con paquetes como ggplot2; RStudio es su IDE |
| Scala | Lenguaje de propósito general, de tipado estático, con programación orientada a objetos y funcional; útil para grandes conjuntos de datos sin perder rendimiento |
| IBM SPSS Statistics | Paquete estadístico de IBM para gestión de datos, análisis avanzado y multivariante e inteligencia de negocio, que cubre planificación, recopilación, análisis, informes e implementación, con interfaz sencilla |

### Elegir herramientas
- No hay herramienta perfecta: cada una tiene ventajas, desventajas y usos que a veces se solapan. Ejemplo: Python gusta por sus muchas bibliotecas; Excel, por sus gráficos integrados.
- Preguntas que una empresa se plantea: qué tipos de datos se analizarán, si hacen falta procesos como el modelado, cuál es el volumen (¿big data?), qué visualizaciones se necesitan (¿interactivas?), qué nivel técnico y qué perfiles las usarán (científicos de datos o personal de marketing) y cuál es el presupuesto.

| Etapa del proyecto | Preguntas | Técnicas | Herramientas |
|---|---|---|---|
| Determinar el problema | ¿Cuál es el problema de negocio? | Formular preguntas, 5 Por qué | Pensamiento de diseño |
| Recopilar y limpiar datos | ¿Dónde están, son correctos, cómo se recopilan, qué cambiar? | Recopilación y limpieza de datos estructurados y no estructurados | SQL, NoSQL, Excel, Google Sheets |
| Analizar datos | ¿Qué destaca? | Regresión, clasificación, agrupamiento; visualizaciones iniciales para ver tendencias | Python, IBM Watson Studio, IBM SPSS, RStudio |
| Validar análisis y modelo | ¿Resuelve el problema? ¿Tienen sentido los resultados? | Machine learning, modelos de negocio | Python, IBM Watson Studio, IBM SPSS, RStudio |
| Visualizar datos | ¿Cuál es la mejor forma de representarlos y conectan con el problema? | Narración, comunicación de información, presentación de hallazgos | Tableau, Matplotlib, Microsoft PowerPoint |

- Es solo una muestra de alineación; hay muchas más herramientas.
- Para elegir qué aprender: las aplicaciones suelen ser más fáciles pero más limitadas; los lenguajes y bibliotecas cuestan más pero dan más flexibilidad. Muchas herramientas no exigen saber programar y ofrecen prueba gratuita o tutoriales.

## Herramientas
Ver la tabla del tema "Herramientas para analizar y visualizar" y la de "Otras tecnologías".

## Preguntas de repaso
1. **¿Cuáles son los cuatro aspectos clave del software de código abierto?**
   Usar, ver, modificar y compartir; todo bajo una licencia y con un propósito común.
2. **¿Qué diferencia hay entre Git y GitHub?**
   Git es un sistema de control de versiones que se instala localmente; GitHub es un servicio en línea para alojar repositorios y colaborar. Git puede usarse sin GitHub, pero no al revés.
3. **¿Cuándo se usa SQL y cuándo NoSQL?**
   SQL para datos estructurados en bases relacionales; NoSQL para datos no estructurados en bases no relacionales, útil en big data y aplicaciones web en tiempo real.
4. **¿Qué ofrece Data Refinery dentro de IBM Watson Studio?**
   Preparar y transformar datos crudos en datos de alta calidad, ver su distribución con gráficos integrados y programar trabajos repetibles.
5. **Nombra tres factores que una empresa considera al elegir herramientas de datos.**
   Cualquiera de: tipo de datos, procesos necesarios como modelado, volumen (big data), visualizaciones requeridas, nivel técnico y perfil de los usuarios, presupuesto.
