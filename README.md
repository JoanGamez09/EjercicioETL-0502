# Análisis de Películas en DynamoDB

## Descripción del Proyecto

Este notebook de AWS Glue permite realizar un procesamiento avanzado sobre una tabla de películas almacenada en DynamoDB. Se realizan dos tareas principales:

  Consulta de la clasificación más repetida en la base de datos y almacenamiento del resultado en un bucket S3.

  Clasificación automática del género de las películas en base a su título y almacenamiento en una nueva tabla en DynamoDB.

## Tecnologías Utilizadas

  AWS Glue (para procesamiento de datos en la nube)

  DynamoDB (base de datos NoSQL para almacenar las películas)
  
  S3 (para almacenamiento de datos procesados)
  
  PySpark (para manipulación y análisis de datos)
  
  AWS Glue Crawler (para indexar la tabla en el Glue Catalog)
  
  Amazon S3 Static Website (para mostrar los datos en una web) 


## Flujo del Notebook

1️⃣ Carga de Datos desde AWS Glue Catalog

Antes de cargar los datos, se ejecutó un AWS Glue Crawler para indexar la tabla en el Glue Catalog.
El notebook inicia cargando los datos de DynamoDB mediante el Glue Catalog.


2️⃣ Consulta de la Clasificación Más Repetida

Se agrupan los datos para determinar cuál es la clasificación más frecuente en la tabla

Luego, el resultado se almacena en un archivo JSON dentro de un S3 bucket.



3️⃣ Clasificación de Género Basado en el Título

Se define una función para categorizar las películas según palabras clave en sus títulos.

Se aplica esta función a la columna "nombre" para clasificar cada película.


4️⃣ Almacenamiento de Resultados en DynamoDB

El resultado se almacena en una nueva tabla llamada Peliculas_Generos_Joan en DynamoDB.


5️⃣ Creación de una Página Web Estática

Se configuró un Amazon S3 Static Website Hosting para mostrar los resultados almacenados en S3 en una página web pública. La web consulta el archivo JSON generado en S3 y lo muestra en un formato amigable.

![Captura](https://github.com/user-attachments/assets/5f1956be-bd32-4cb7-80d9-cb6d1465d0ec)






