# Proyecto ETL - Análisis de Precios de Medicamentos en Colombia

Este proyecto tiene como objetivo desarrollar una solución ETL para centralizar, transformar y estandarizar los precios de los medicamentos en Colombia para mejorar la toma de decisiones informadas en el sector de la salud y por parte de los consumidores.

## Ejecucion del proyecto

Este proyecto se puede abrir en google colab en el siguiente link: [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/njacob1001/etl-project/blob/main/notebooks/proyectoETL.ipynb)

## Requerimientos

- Python 3.x
- Pandas
- Matplotlib
- SQLite
- Otros paquetes necesarios: scipy, numpy, etc.

## Descripción del Proyecto

La gestión y el análisis de los precios de medicamentos en Colombia es un desafío crítico debido a la variabilidad y dispersión de los datos disponibles. Los precios de los medicamentos varían significativamente dependiendo del canal de distribución (institucional vs. comercial). Este hecho complica aún más el análisis, ya que los datos no solo están dispersos en diversas fuentes, sino que también presentan inconsistencias debido a la fuente de los datos y las diferencias entre los canales de distribución.

### Objetivos del Proyecto

#### Objetivo General:
Desarrollar una solución ETL para centralizar, transformar y estandarizar los precios de los medicamentos en Colombia para mejorar la toma de decisiones informadas en el sector de la salud y por parte de los consumidores.

#### Objetivos Específicos:
- Identificar y seleccionar las fuentes de datos más relevantes para el análisis de precios de medicamentos en Colombia.
- Desarrollar el proceso ETL para integrar y limpiar los datos, eliminando inconsistencias y valores atípicos.
- Realizar un análisis exploratorio de los precios de los medicamentos, identificando patrones y diferencias entre los canales institucional y comercial.
- Generar un conjunto de datos estandarizado y centralizado para su posterior análisis y comparación de precios.
- Proporcionar recomendaciones basadas en los datos para mejorar la transparencia de precios y la competitividad en el mercado farmacéutico colombiano.

## Fuentes de Datos

El análisis se basa en varios datasets proporcionados por diferentes fuentes:

1. **[Precios Medicamentos - Datos Abiertos](https://www.datos.gov.co/Salud-y-Protecci-n-Social/Precios-Medicamentos/3t73-n4q9/about_data)**
2. **[Clicsalud - Termómetro de Precios de Medicamentos](https://www.datos.gov.co/Salud-y-Protecci-n-Social/Clicsalud-Term-metro-de-Precios-de-Medicamentos/n4dj-8r7k/about_data)**
3. **[Medicamentos (Comparativa de Precios)](https://www.datos.gov.co/Salud-y-Protecci-n-Social/medicamentos/ec4u-mzse/about_data)**

Estos datasets fueron seleccionados por su relevancia para el análisis de precios de medicamentos, aunque algunos datasets fueron descartados por la falta de información relevante (por ejemplo, la variable precios de medicamentos, en los datasets analizados).

## Proceso ETL

## Enlace al PDF del Proceso ETL

Puedes consultar el *proceso completo del ETL* en el siguiente [enlace al PDF](https://drive.google.com/file/d/1XDmF_xA6dVcheQ4hQEvq--4DgckCR6f5/view?usp=sharing).


## Imagen del Flujo ETL

Aquí se muestra el diagrama del flujo completo del proceso ETL para ilustrar la secuencia de pasos involucrados:

![Flujo ETL](https://drive.google.com/uc?export=view&id=1ehGVew_vNpEeiV0-nDoXYC0J_5O-jizZ)


### Extracción
- Se utilizaron varios datasets en formato CSV, que contienen información sobre los precios de los medicamentos en Colombia, junto con detalles adicionales como principio activo, fabricante, y otros.

### Transformación
- *Renombrado de columnas*: Para unificar las columnas entre los diferentes datasets, se renombraron ciertas columnas.
- *Conversión de datos*: Las columnas numéricas como precio_por_tableta fueron convertidas al tipo de dato adecuado (flotante) para permitir el análisis numérico.
- *Limpieza de datos*: Se eliminaron los registros duplicados y los valores nulos fueron verificados y manejados. También se gestionaron los outliers (valores atípicos) utilizando métodos estadísticos como IQR y Z-score.

### Carga
- Los datos transformados y limpios fueron almacenados en una base de datos *SQLite* denominada *medicamentos.db*, la cual contiene las tablas con la información estandarizada y centralizada.

## Análisis de Datos

### Promedio de Precios por Medicamento
Se identificaron los 10 medicamentos con los precios promedio más altos, destacando productos como *Zebesten, **Biovisc, y **Doxorubicina Clorhidrato*.

### Distribución de Precios
Un análisis de la distribución de los precios mostró que la mayoría de los precios están concentrados en el rango bajo, con una pequeña cantidad de medicamentos con precios extremadamente altos.

### Precio Promedio por Canal
Se identificó que el canal comercial tiene un precio promedio más alto (6,926 COP por tableta) en comparación con el canal institucional (5,792 COP por tableta).

## Recomendaciones

1. *Revisión de la Regulación de Precios de Medicamentos de Alto Costo*:
   Se sugiere implementar políticas de control de precios para medicamentos de alto costo, para reducir las disparidades en los precios entre diferentes medicamentos.

2. *Fomento de la Competencia en el Canal Comercial*:
   Crear incentivos para mejorar la competitividad en el canal comercial, con el fin de reducir la brecha de precios entre el canal institucional y comercial.

3. *Establecer un Sistema de Información Transparente sobre Precios*:
   Desarrollar una plataforma pública que permita a los consumidores comparar los precios de los medicamentos en tiempo real y tomar decisiones más informadas.


