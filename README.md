# Proyecto Individual 1- Data 04- Soy Henry   
## Data Engineering
![image](https://user-images.githubusercontent.com/108296379/182138583-9011699a-f009-4454-885e-80dca182b6c8.png)


##  Propuesta hecha por Henry en el Marco de LABS 
Bienvenidx! Este repo mismo fue realizado en base al proyecto propuesto por Henry en el Bootcamp de DataScience. 
El mismo plantea el siguiente problema: ¨En este primer proyecto proponemos realizar un proceso de ETL (extract, transform and load) a partir de un conjunto de datos que se enfocarán en una misma perspectiva de negocio. Los datos vienen de diversas fuentes de relevamiento de precios en distintos mercados. Deberán trabajar los diferentes tipos de archivos para llevarlos a una misma extensión y, una vez finalizada esta etapa, deberán crear los joins necesarios con el objetivo de crear un DER y dejarlos almacenados en un archivo con extensión .db. Por último, todo su trabajo deberá contemplar la carga incremental del archivo "precios_semana_20200518.txt".
En este repositorio encontrarán todo lo necesario para abordar la próblematica y darle una solución.
Tener en cuenta que sí se desea clonar/forkear este repositorio, se debe instalar Python y varias dependencias, cómo así también un motor de base de datos. 

## Herramientas utilizadas:

 - Python y sus librerías, cómo Pandas y SQLalchemy
 - Gestor SQL: MySQL
 - Jupyter Notebook 


## Flujo de trabajo

En la siguiente imagen se pueden ver el flujo completo de los datos a tráves del pipeline y las herramientas útilizadas en cada uno.

![image](https://i.ibb.co/4F2F0tC/Diagrama-Pipeline.png)

### Pasos de forma detallada

#### Extración (E)

La extración se hace de una carpeta llamada Dataset_relevamiento_precio. Esta carpeta cuenta con archivos de distinto tipo tanto binario cómo de texto.

Los archivos de texto se exáminaron para saber los tipos de separadores que tenian.

Para poder leer los archivos correctamente, se recurre a la librería de Pandas, qué nos permite manipular archivos con distinta extensión y convertirlos a tablas llamadas dataframes, haciendo más simple su procesamiento. 

#### Tránsfomación (T)

Ahor que tenemos los datos en tablas, hacemos un pequeño paneo de cómo se componen.
Lo primero que se hace es ver los nulos y duplicados las tablas y cuantificar un % en caso de que necesitemos presentarlo al cliente. 
Se pone un critério para cada tipo de dato, en caso de tener valores de tipo monetario, se pasan a flotantes.
Por último se intenta a través de distintos métodos o funciones que los datos queden lo más estandarizados posibles. Por ej que el código EAN tenga siempre 13 dígitos. También se limpian espacios en blanco que no corresponden y algunos valores con error de carga.

#### Carga (Load - L)

Una vez tenemos los datos limpios, podemos disponibilizarlos para su consumo. Utlizaremos MySQL para almacenar los datos y haremos la conexión a tráves de SQLalquemy, una librería de Python.
Primero, se crearan las tablas con sus tipos de datos acordes. 
Se cargan los datos transformados y guardados en el dataframe directo a la base de datos, utilizando una conexión con SQLalquemy. 
Una vez cargados todos los datos en sus tablas, se pueden hacer algunas queries para asegurarse que todo se encuentra funcionando bien. 

    
## Objetivos alcanzados
- Procesar los diferentes datasets. 
- Crear un archivo SQL con las tablas (equivalente a .DB). Se adjunta el archivo con las tablas vácias que se pueden ir completando con el notebook de python.
- Realizar en draw.io un diagrama de flujo de trabajo del ETL. El archivo se encuentra adjunto como ¨Diagrama_flujo.drawio¨ y se muestra arriba.
- Se realiza una carga incremental final que es el último paso del notebook.
- Se hicieron pruebas luego de la carga en el gestor de base de datos Workbench y las consultas 

