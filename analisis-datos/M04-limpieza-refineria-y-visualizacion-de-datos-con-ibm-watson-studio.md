# Data Fundamentals - M04 Limpieza, refinería y visualización de datos con IBM Watson Studio

## Resumen
El módulo es práctico: con IBM Watson Studio y su herramienta Data Refinery se trabaja un caso de fraude en seguros de automóviles. Se prepara el servicio, se carga un CSV de reclamaciones, se limpia (columnas sin valor predictivo, datos personales, tipos de datos), se crea una columna nueva para probar una hipótesis del patrocinador y se visualiza con un gráfico de dispersión. La conclusión es que las reclamaciones altas suelen ser fraude, pero no siempre.

## Conceptos clave
- **IBM Watson Studio:** IDE colaborativo para ciencia de datos, ML e IA, que incluye Data Refinery.
- **Data Refinery:** herramienta interactiva, sin código, para limpiar, dar forma y visualizar datos (más de 100 operaciones integradas).
- **Datos predecibles:** columnas que pueden ayudar a anticipar el fenómeno de interés; las demás se descartan.
- **Información personal (PII):** datos que identifican a una persona; hay que vigilar su uso.
- **Data profile:** estadísticas descriptivas que calcula la herramienta por columna.
- **Hipótesis:** supuesto del patrocinador que se pone a prueba con los datos.
- **Variable independiente y dependiente:** la que se usa para explicar (eje X) y la que se observa (eje Y).

## Detalle por tema

### IBM Watson Studio y Data Refinery
- Es un entorno único para preparar y analizar datos, crear y entrenar modelos y compartir resultados, de modo que no se parte de cero ante cada problema.
- Ofrece a los científicos de datos un proceso simplificado, entorno colaborativo, visualizaciones fáciles, acceso a herramientas de código abierto y desarrollo, entrenamiento, gestión e implementación de aplicaciones con IA.
- **Data Refinery** ahorra tiempo de preparación: permite crear un flujo de limpieza, entender calidad y distribución con gráficos, tablas y estadísticas integrados, programar trabajos repetibles y visualizar datos.

### Caso del proyecto
- **Contexto:** una aseguradora de automóviles ofreció plataformas en línea y móviles para reclamar; las transacciones son más rápidas, pero los procesadores tienen menos tiempo para detectar fraudes, que ya costaron millones de dólares.
- **Objetivo:** predecir fraudes y actividad sospechosa para reducir las pérdidas.
- **Patrocinadora:** la directora del Departamento de reclamaciones fraudulentas.
- **Datos:** CSV ficticio basado en el registro de eventos de una aseguradora real, con 975 filas y 38 columnas; cada fila es la reclamación ya aprobada de una persona tras un accidente.
- **Contexto de seguros:** la póliza suele ser de seis meses, con prima mensual o única; el costo depende del tipo de vehículo, del historial y de la edad del conductor (los adolescentes son más riesgosos); pagan menos quienes tienen pocos accidentes y multas, conducen poco, toman cursos de educación vial o aseguran varios autos.
- **Tareas:** aprovisionar el servicio, configurar el proyecto, importar datos, limpiar, refinar y crear una visualización.

### Limpieza de datos
- Se eliminan los datos "ruidosos" (no necesarios ni útiles) y se conservan los que ayuden a predecir fraude.
- Criterio: preguntarse para cada columna si sus datos permiten predecir fraude.
- **Eliminar:**
  - columnas de identificadores (HOUSEHOLD_ID, DRIVER_ID, POLICY_ID, CLAIM_ID, PRIMARY_DRIVER_ID), pues solo cuentan filas y no predicen;
  - columnas vacías (DESCRIPCIÓN);
  - información personal (nombres, apellidos y similares).
- **Conservar:** causa del incidente (INCIDENT_CAUSE), estado de la reclamación (CLAIM_STATUS), kilometraje (ODOMETER_AT_LOSS), fechas y horas (LOSS_EVENT_TIME, CLAIM_INIT_TIME), denuncia policial (POLICE_REPORT, 0 o 1) y monto reclamado (CLAIM_AMOUNT).
- **FLAG_FOR_FRAUD_INV:** marca (0 o 1) que los investigadores de fraude asignaron al final del año; son las respuestas conocidas y sirven de datos de entrenamiento para un modelo de aprendizaje supervisado. Se conserva y se usa luego en la visualización.
- Mantener columnas de fecha y hora tiene sentido por curiosidad: tardar mucho en reclamar podría significar algo.
- **Información personal:** cualquier dato sobre una persona viva identificable (nombre, teléfono, correo, matrícula, fecha de nacimiento). Hay que tener cuidado con ella y con si se permite usarla; aquí tampoco predice fraude.
- **Tipos de datos:** se verifica que cada columna tenga el tipo correcto. LOSS_EVENT_TIME venía como cadena (secuencia de letras, dígitos y signos) y se convierte a fecha para poder calcular con ella.
- Guardar con frecuencia. Al terminar, se guarda y se crea un trabajo que genera un CSV nuevo con sufijo "_shaped" como archivo de trabajo futuro.
- La limpieza es un paso largo e importante del proyecto.

### Refinación con una hipótesis
- **Hipótesis de la patrocinadora:** las reclamaciones de reparación superiores a 10 000 dólares pueden ser fraudulentas y servir para predecir fraude.
- Con 19 columnas tras la limpieza, se calcula una columna nueva que indica si CLAIM_AMOUNT supera 10 000. Sale con valores verdadero o falso (booleano) y se convierte a entero: 0 si no supera el umbral y 1 si lo supera.
- Se podrían explorar otras hipótesis, como que conducir con licencia vencida ayude a predecir fraude.

### Visualización
- La pestaña Visualizaciones está disponible tras cargar datos. Una visualización no sale perfecta de entrada: hay que probar gráficos y combinaciones de ejes.
- Se elige un gráfico de dispersión: eje X (variable independiente) con la columna nueva de monto excesivo y eje Y (variable dependiente) con el monto de la reclamación.
- Se añade color según FLAG_FOR_FRAUD_INV: azul para no fraude y rosado para fraude.
- La visualización es interactiva (al pasar el cursor aparecen los puntos) y se guarda en el proyecto para compartirla con el patrocinador.

## Interpretación de resultados
- **Perfil de datos:** una columna con desviación estándar suele tener datos de interés; una sin variación, solo con conteos de filas, no aporta. La desviación estándar mide la dispersión respecto a la media (baja: datos agrupados; alta: datos más dispersos).
- **Gráfico de dispersión de la hipótesis:**
  - Hay reclamaciones menores a 10 000 que no son fraude (ejemplo: 1 720) y otras que sí lo son (ejemplo: 2 730).
  - Hay muchas reclamaciones sobre 10 000 que son fraude, lo que respalda la hipótesis.
  - También hay reclamaciones sobre 10 000 que no son fraude, así que no todas son fraudulentas.
- Conclusión del módulo: se trabajó con las reclamaciones de 975 clientes y la hipótesis del umbral es útil pero no concluyente por sí sola.

## Herramientas
- **IBM Watson Studio** (sobre IBM Cloud / Cloud Pak for Data) y su **Data Refinery**.
- **IBM Cloud Object Storage:** almacenamiento del proyecto, capaz de guardar datos no estructurados como imágenes y texto.
- Datos en formato **CSV** (valores separados por comas).

## Laboratorio
Simulación guiada con IBM Watson Studio.
1. **Preparación:** desde el catálogo de IBM Cloud se aprovisiona Watson Studio (ubicación Dallas, plan gratuito, nombre "Watson Studio-AutoIns"), se crea un proyecto vacío ("Seguro de automóviles") y se sube el archivo AutoInsClaims.csv.
2. **Comprensión y limpieza:** en la herramienta se usan las pestañas Datos, Perfil y Visualizaciones; se eliminan columnas de identificadores, vacías y de información personal (de 38 a 34 columnas en el primer tramo), se convierte LOSS_EVENT_TIME a fecha y se guarda como trabajo ("Predicción de fraude en seguros de automóviles").
3. **Refinación:** sobre el CSV "_shaped" (19 columnas) se calcula EXCESSIVE_CLAIM_AMOUNT (mayor que 10000) y se convierte a entero.
4. **Visualización:** se crea el gráfico de dispersión coloreado por FLAG_FOR_FRAUD_INV y se guarda en el proyecto.
- **Resultado:** conjunto limpio y refinado, y una visualización que muestra que muchas reclamaciones sobre 10 000 son fraude, aunque no todas.

## Preguntas de repaso
1. **¿Qué ofrece Data Refinery en IBM Watson Studio?**
   Un flujo para limpiar y dar forma a los datos sin programar, estadísticas y gráficos para ver calidad y distribución, trabajos programables y visualizaciones, con más de 100 operaciones integradas.
2. **¿Por qué se eliminan las columnas de identificadores, las vacías y la información personal en este proyecto?**
   Porque no ayudan a predecir fraude: los identificadores solo cuentan filas, las vacías no aportan y los datos personales no son predictivos y además exigen cuidado en su uso.
3. **¿Para qué sirve la columna FLAG_FOR_FRAUD_INV?**
   Contiene la conclusión de los investigadores (0 no fraude, 1 fraude), son las respuestas conocidas que sirven como datos de entrenamiento supervisado y para colorear el gráfico.
4. **¿Cómo se prueba la hipótesis de las reclamaciones sobre 10 000 dólares?**
   Se calcula una columna nueva (mayor que 10000), se convierte a 0 o 1 y se grafica contra el monto en un gráfico de dispersión coloreado por la marca de fraude.
5. **¿Qué concluye la visualización?**
   Muchas reclamaciones superiores a 10 000 son fraude, pero algunas no, y hay fraudes por debajo de ese monto, así que el umbral por sí solo no basta.
