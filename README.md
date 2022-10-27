# Proyecto Individual 1- Data 04- Soy Henry   
## Data Engineering
![image](https://user-images.githubusercontent.com/108296379/182138583-9011699a-f009-4454-885e-80dca182b6c8.png)


##  Propuesto por Henry en el Marco de LABS 
¨En este primer proyecto proponemos realizar un proceso de ETL (extract, transform and load) a partir de un conjunto de datos que se enfocarán en una misma perspectiva de negocio. Los datos vienen de diversas fuentes de relevamiento de precios en distintos mercados. Deberán trabajar los diferentes tipos de archivos para llevarlos a una misma extensión y, una vez finalizada esta etapa, deberán crear los joins necesarios con el objetivo de crear un DER y dejarlos almacenados en un archivo con extensión .db. Por último, todo su trabajo deberá contemplar la carga incremental del archivo "precios_semana_20200518.txt".

En esta etapa de la academia, verán siempre la palabra "Plus", que hará referencia a los puntos extra disponibles para cada trabajo. Es muy importante que estos sean obviados hasta completar los requerimientos mínimos (deben entregar siempre el producto mínimo viable, MVP, que hace lo mínimo que pedimos), pero siempre recomendamos tratar de completar los plus/adicionales aún después de que el trabajo haya sido entregado, ya que generarán valor agregado a su portfolio.¨
    
## Objetivos alcanzados
- Procesar los diferentes datasets. 
- Crear un archivo SQL con las tablas (equivalente a .DB). Se adjunta el archivo en 
- Realizar en draw.io un diagrama de flujo de trabajo del ETL. El archivo se encuentra adjunto como ¨Diagrama_flujo.drawio¨
- Se realiza una carga incremental final que es el último paso del notebook.
- Se hicieron pruebas luego de la carga en el gestor de base de datos Workbench y las consultas 

## Glosario del trabajo:

### Diccionario de datos

Archivos con los relevamientos semanales (ej: precio_semana_20200518.txt)
~~~
Precio: Precio del producto en pesos argentinos.
Vpn_keyproducto_id: Código EAN del producto.
Text_formatsucursal_id: ID de la sucursal. Los dos primeros números determinan la cadena.
~~~

~~~
Productos.parquet  

id: Código EAN del producto.
marca: Marca del producto.
nombre: Detalle del producto.
Presentación: Unidad de presentación del producto.
categoria1: categoria a la que pertenece el producto.
categoria2: categoria a la que pertenece el producto.
categoria3: categoria a la que pertenece el producto.
~~~

~~~
Sucursales.csv  

Id: Es el ID principal, compuesto por la concatenación de banderaId-comercioId-sucursalId.
comercioId: es el identificador de la empresa controlante. Por ejemplo Hipermecado Carrefour y Express tienen mismo comercioId pero distinta banderaId
banderaId: Diferencia las distintas "cadenas" de la misma empresa. Vea, Disco y jumbo pertenecen al mismo comercio pero tienen distinta bandera.
banderaDescripcion: Nombre de fantasía de la Cadena
comercioRazonSocial: Nombre con la que está registrada legalmente la empresa.
provincia: Provincia donde está ubicado el comercio.
localidadl: Localidad donde está ubicado el comercio.
direccion: Dirección del comercio,
lat: Coordenadas de latitud de la ubicación del comercio
lng: Coordenadas de longitud de la ubicación del comercio
~~~


![image](https://i.ibb.co/4F2F0tC/Diagrama-Pipeline.png)

![image](https://i.ibb.co/wg7XKZ6/Captura-de-Pantalla-2022-10-27-a-la-s-10-19-07.png)

