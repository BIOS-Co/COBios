# COBios
En este repositorio tenenemos el estudio realizado al cuestionario "Sobre mi trabajo" que evalua el clima organizacional, diseñado por la organización panamericana de la Salud (OPS). Consta de 80 preguntas que representan la evaluación de 4 áreas críticas para describir el clima de una institución: liderazgo, motivación, reciprocidad y participación. Cada una de ellas se desglosa en 4 subvariables para un mejor análisis de las mismas y por cada subvariable existen 5 afirmaciones en el cuestionario, intercalandose de forma aleatoria e instrumentándose de la siguiente forma:

1) Liderazgo:

- Dirección [1 - 14 - 33 - 51 - 67]
- Estímulo a la excelencia [15 - 30 - 34 - 52 - 70]
- Estímulo al trabajo en equipo [2 - 17 - 35 - 50 - 73]
- Solución de conflictos [16 - 31 - 36 - 55 - 68]

2) Motivación: 

- Realización personal [3 - 18 - 37 - 49 - 74]
- Reconocimiento de la aportación [19 - 32 - 40 - 56 - 69]
- Responsabilidad [4 - 20 - 43 - 57 - 75]
- Adecuación de las condiciones de trabajo [5 - 21 - 41 - 59 - 65]

3) Reciprocidad: 

- Aplicación al trabajo [6 - 22 - 42 - 58 - 71]
- Cuidado del patrimonio institucional [7 - 23 - 44 - 60 - 72]
- Retribución [8 - 24 - 39 - 54 - 66]
- Equidad [9 - 25 - 45 - 53 - 76]
4) Participación:
- Compromiso con la productividad [10 - 26 - 46 - 61 - 77]
- Compatibilidad de intereses [11 - 27 - 47 - 62 - 78]
- Intercambio de información  [12 - 28 - 48 - 63 - 79]
- Involucración al cambio [13 - 29 - 38 - 64 - 80]  

Cada una de las preguntas genera un punto en la subvariable de la categoria con un total de 5, y la nota del criterio sale de un promedio entre las 4 subvariables, dicho data set se encuentra definido en la carpeta de Data con el nombre de Cuestionario_Clima_2023_Co_Depurado (1).xlsx ahí se agrega una columna de id al final del todo para categorizar a los sujetos.

# Estructura de las carpetas del proyecto
Dentro del repositorio tenemos 4 carpetas:

- Data: Contiene la base de datos utilizada para entrenar cada uno de los modelos y que corresponde al test generado mas ciertas variables categoricas de la persona.
- Modelos: Carpeta que contiene los modelos en formato joblib debido a que esa esa la libreria que utilizamos internamente para generar, guardar y cargar los modelos construidos para el analisis de la base de datos seleccionada. Tenemos en total 5, donde se incluyen 4 modelos predictivos uno para cada criterio evaluado (Liderazgo,Motivación, Participación y Reciprocidad), y finalmente un modelo de clasificación o cluster.
- ResultadosAnalisisCluster: Carpeta donde se almacenan por defecto los resultados de la agrupación por cluster, aunque se puede cambiar directamente en el codigo fuente ubicado en el archivo ModeloClusterInference.ipynb, los archivos resultantes son archivos xlsx con los datos del usuario y el grupo al cual pertenecen.
- InformesClusters: Para el modelo de cluster generado en el archivo ModeloClusterInference.ipynb se identificaron un total de 7 grupos, por lo tanto se realizo un dashboard pequeño, para cada uno , donde se pueden interpretar las caracteristicas de cada categoria y plantear estrategias determinadas, dichos informes estan registrados en esta carpeta que son formato html y pueden ser abierto en cualquier navegador.
-  CuadernillosGoogleColab: Es la carpeta que contiene los cuadernillos con los cuales se entrenaron los modelos finales, ademas del analisis inspectorio inicial de los datos para evaluar la tipologia de los datos, y su relación con las salidas.

# MODELOS
Finalmente tenemos 5 modelos generados, los primeros 4 corresponden a modelos predictorios con parametros de entrada las variables categoricas de la persona como son [edad, sexo, area de trabajo, institución, etc...] , para poder predecir cual sera su rendimiento en el examen de ambiente laboral en cada una de las areas determinadas,
