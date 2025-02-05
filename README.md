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


## Flujo del Notebook

1️⃣ Carga de Datos desde AWS Glue Catalog

El notebook inicia cargando los datos de DynamoDB mediante el Glue Catalog:


2️⃣ Consulta de la Clasificación Más Repetida

Se agrupan los datos para determinar cuál es la clasificación más frecuente en la tabla:

Luego, el resultado se almacena en un archivo JSON dentro de un S3 bucket.



3️⃣ Clasificación de Género Basado en el Título

Se define una función para categorizar las películas según palabras clave en sus títulos.

Se aplica esta función a la columna "nombre" para clasificar cada película:


4️⃣ Almacenamiento de Resultados en DynamoDB

El resultado se almacena en una nueva tabla llamada Peliculas_Generos_Joan en DynamoDB:





