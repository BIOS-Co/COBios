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
Finalmente tenemos 5 modelos generados, los primeros 4 corresponden a modelos predictorios con parametros de entrada las variables categoricas de la persona como son [edad, sexo, area de trabajo, institución, etc...] , para poder predecir cual sera su rendimiento en el examen de ambiente laboral en cada una de las areas determinadas, para este caso se reemplanteo el problema de regresión a un problema de clasificación, donde cada categoria corresponde a un rango de valores, para la nota de la categoria en estudio, junto a un % de fiabilidad, el modelo se vera ejecutado en un explainer dashboard, donde nos centraremos en 4 secciones proporcionadas:
- Feacture importances: Que es basicamente la sección donde podremos observar, cual fue el peso de cada variable a la hora de generar el modelo, organizado por orden de importancia, para el mismo.
- Individual Predictions: Corresponde al apartado donde podremos ver individualmente, cual es el porcentaje de fiabilidad para cada categoria, a cual categoria fue vinculado, y ademas tendremos manera de ver mediante un Contributions Plot, como fue el proceso para cada categoria, y en que contribuyo para cada variable para ser ubicado en un determinado grupo.
- What if: que corresponde a un entorno de simulación, para generar sujetos y ver como serian clasificados por el modelo.

Cada modelo tiene 5 grupos posibles, pero representan rangos diferentes dependiendo de la categoria organizados de la siguiente manera:

# LIDERAZGO
Categoria 0 [1 - 1.8]
Categoria 1 [1.8 - 2.6]
Categoria 2 [2.6 - 3.5]
Categoria 3 [3.5 - 4.2]
Categoria 4 [4.2 - 5]

# MOTIVACIÓN
Categoria 0 [0.25 - 1.2]
Categoria 1 [1.2 - 2.15]
Categoria 2 [2.15 - 3.1]
Categoria 3 [3.1 - 4.05]
Categoria 4 [4.05 - 5]

# RECIPROCIDAD
Categoria 0 [0.75 - 1.5]
Categoria 1 [1.5 - 2.25]
Categoria 2 [2.25 - 3.0]
Categoria 3 [3.0 - 3.75]
Categoria 4 [3.75 - 4.5]

# PARTICIPACIÓN
Categoria 0 [0.5 - 1.4]
Categoria 1 [1.4 - 2.3]
Categoria 2 [2.3 - 3.2]
Categoria 3 [3.2 - 4.1]
Categoria 4 [4.1 - 5]

# MODELO DE CLUSTER
Este modelo que se ubica en el archivo ModeloClusterInference.ipynb , corresponde como dice la extensión a un cuadernillo en formato ipynb, y es un modelo de aprendizaje no supervisado, mas especificos de cluster, basicamente el estudio que se realizo en este aspecto, fue identificar grupos teniendo en cuenta las caracteristicas de las personas, y los resultados en las areas determinadas, para poder observar tendencias y las caracteristicas de cada uno de estos grupos, de esta manera identificar falencias y generar un plan de acción para cada uno.

Como entrada recibe un archivo xlsx que contiene el mismo formato que la data original, ubicado en la carpeta Data, y cuya ruta se estipula en la variable folder_path del archivo ipynb, en la sección de subir archivo. Finalmente el modelo devuelve un archivo xlsx que por default tiene el nombre de  ResultadosClusters.xlsx dentro de la carpeta ResultadosAnalisisCluster, con la categoria asignada a cada clase. para poder entender cuales son las dificultades de cada clase, vienen los informes asociados dentro de la carpeta informes clusters.

# Requerimientos

1) Instala un lector de codigó con compatibilidad con jupyterNotebooks, preferiblemente Visual Studio Code.
- https://code.visualstudio.com/
- Instala el gestor de paquetes de python (pip), para poder instalar las dependencias de necesarias de los cuadernillos que contienen los modelos
2) Instala las extensiones de Python, Jupyter, Jupyter Keymap, Jupyter Slide Show, Jupyter cell tags, Jupyter Notebook Renderers.
3) Clona el repositorio mediante el comando en consola:
"git clone https://github.com/BIOS-Co/COBios.git"

4) Abre la carpeta del proyecto en visual studio denominada COBios.
5) En caso de ser necesario instala el kernel de jupyter notebook que te recomiendan como sugerencia el visual studio code.
6) Instala los siguiente paquetes en tu computadora mediante el comando "pip install" en consola
- pip install pandas
- pip install matplotlib
- pip install seaborn
- pip install numpy
- pip install sklearn
- pip install statsmodels
- pip install explainerdashboard
- pip install catboost
- pip install xgboost
- pip install joblib

# Modelos XGBOOST [liderazgo, motivación, reciprocidad, participación]
Finalizado los pasos anteriores para ejecutar el modelo, debes acceder al archivo del modelo que no se encuentra ubicado en ninguna carpeta, con formato ipynb, ejecuta el comando Run All que se encuentra en la parte superior del visual, al final del codigo que tarda unos minutos en ejecutarse donde se ubica el comando  db.run(), ahí se generara un dashboard, en un puerto local definido de la siguiente forma 

Starting ExplainerDashboard on http://192.168.1.21:8050
Dash is running on http://0.0.0.0:8050/

los puerto pueden cambiar, pero accediendo a cualquier de dichos enlaces podras ver el tablero asociado al modelo ejecutado.

# Modelo de cluster

