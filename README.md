<h1 align='center'>
 <b>Proyecto de Análisis de Datos</b>
</h1>
 
# <h1 align="center">**`SINIESTROS VIALES EN CABA`**</h1>


<p align='center'>
<img src = 'imagenes\istockphoto-1188671707-170667a.jpg' height = 500>
<p>


# Introducción

En este informe, se presenta un análisis de datos sobre homicidios en siniestros viales ocurridos en la Ciudad Autónoma de Buenos Aires (CABA) durante el período comprendido entre 2016 y 2021. 

**El objetivo principal de este proyecto es proporcionar información crucial que permita a las autoridades locales tomar medidas efectivas para reducir la cantidad de víctimas fatales en siniestros viales en la ciudad.**

**Producto final:** [DASHBOARD](homicidios_viales.pbix)

# Contexto

Los siniestros viales, también conocidos como accidentes de tráfico o accidentes de tránsito, son eventos que involucran vehículos en las vías públicas y pueden tener diversas causas, como colisiones entre automóviles, motocicletas, bicicletas o peatones, atropellos, choques con objetos fijos o caídas de vehículos. Estos incidentes pueden tener consecuencias que van desde daños materiales hasta lesiones graves o fatales para los involucrados.

La Ciudad Autónoma de Buenos Aires, no es la excepción a esta problemática, dado el alto volumen de tráfico y la densidad poblacional. Estos incidentes pueden tener un impacto significativo en la seguridad de los residentes y visitantes de la ciudad, así como en la infraestructura vial y los servicios de emergencia.

# Datos

Para llevar a cabo este proyecto, se utilizaron principalmente 2 conjuntos de datos disponibles en la página de Gobierno de la Ciudad de Buenos Aires, que se encuentran en formato Excel:

- **HECHOS**: Esta planilla contiene información detallada sobre cada siniestro vial con un ID único y diversas variables relacionadas con el tiempo, el espacio y los participantes en el incidente.
- **VICTIMAS**: Aquí se registran los datos de cada víctima involucrada en los hechos, incluyendo edad, sexo y modo de desplazamiento. Esta pestaña está vinculada a la pestaña HECHOS a través del ID del siniestro.

Los archivos se obtuvieron de la página de Gobierno de la Ciudad de Buenos Aires, la cual proporciona una base de datos libre y accesible para su análisis. Puede encontrarse más información y acceder a los datos en [este enlace](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales).

Además, es importante destacar que se cruzaron estos datos con la información de población de la Ciudad de Buenos Aires proporcionada por el Instituto Nacional de Estadística y Censos (INDEC). Necesaria para calcular los KPIs. Se puede acceder a la misma [aquí](https://www.indec.gob.ar/ftp/cuadros/poblacion/proy_1025_depto_caba.xls).

# Tecnologías Utilizadas
Para la realización de este proyecto se emplearon las siguientes tecnologías y herramientas:

- **Python, Pandas y Numpy**: Se utilizaron para llevar a cabo los procesos de extracción, transformación y carga de los datos, así como para realizar el análisis exploratorio de los mismos.

- **Librerías de Visualización Gráfica en Python**: Se emplearon diversas librerías de visualización gráfica en Python, como Matplotlib y Seaborn, para crear visualizaciones informativas y representativas de los datos.

- **Power BI**: Se utilizó Power BI para construir un dashboard interactivo que facilita la interpretación de la información y el análisis de los resultados del proyecto.


# Anáisis Exploratorio de los Datos (EDA)
Para este proyecto, se realizó un exhaustivo preprocesamiento de los datos con el objetivo de alcanzar la estructura más adecuada para un análisis efectivo, alineado con el objetivo principal.

En primer lugar, se realizó un proceso de Extracción, Transformación y Carga (ETL) de los datos, tanto de "HECHOS" como "VÍCTIMAS", donde se estandarizaron los nombres y los tipos de datos de las variables, se analizaron los valores faltantes y duplicados,  se eliminaron columnas redundantes y se crearon nuevas caracteristicas derivadas de los datos con el fin de mejorar los resultados del análisis. Una vez finalizado este proceso para los dos conjuntos de datos, se procedió a unirlos en un solo DataFrame denominado *homicidios*.

En segundo lugar, se realizó un Análisis Exploratorio de Datos (EDA) exhaustivo para encontrar patrones que permitieran generar información que ayudara a las autoridades locales a tomar medidas efectivas para disminuir la cantidad de víctimas fatales en siniestros viales.

El EDA incluyó una serie de análisis estadísticos de variables numéricas y la creación de diversas visualizaciones gráficas con el objetivo de comprender en profundidad el impacto de las diferentes variables en los homicidios en siniestros viales. Esta etapa de análisis tenía como finalidad generar posibles insights que luego podrían ser profundizados en un dashboard interactivo.

Estos análisis proporcionaron una base sólida para comprender la dinámica de los homicidios en siniestros viales en la Ciudad Autónoma de Buenos Aires y establecer áreas clave en las que las autoridades locales podrían enfocarse para implementar medidas preventivas y de seguridad vial. Los insights obtenidos durante esta etapa se utilizaron para diseñar un dashboard interactivo que permitiera una exploración más detallada de los datos y la toma de decisiones informadas.

Acceda [AQUÍ](EDA.ipynb) al archivo completo.

# Análisis de los Datos

## Distribución Temporal

- La distribución anual de la cantidad de víctimas fatales muestra una leve tendencia a la baja, sobre todo a partir del año 2019.

- Entre los meses, Diciembre muestra una notoria diferencia respecto a los demás, fueron 87 los homicidos totales en este mes contra 61 en promedio del resto.

- En la distribución de víctimas a lo largo de la semana, no se observan diferencias significativas entre los días. Esto sugiere que el riesgo de siniestros viales con víctimas fatales se mantiene relativamente constante a lo largo de la semana, sin presentar picos notorios en días específicos.
<p align='center'>
<img src = 'imagenes\tiempo.png' height = 500>
<p>

## Perfil de las Víctimas
- El 77% de las víctimas fatales son de sexo masculino.
- La edad promedio de las víctimas es de 42 años. El 40,2 % tenía entre 16 y 35 años.

<p align='center'>
<img src = 'imagenes\genero_edad.png' height = 400>
<p>


## Distribución Espacial y Rol de la Víctima 
- El 62% de las víctimas fatales perdieron la vida en avenidas.
- El 42 % de las víctimas fueron motociclistas y el 37 % peatones

<p align='center'>
<img src = 'imagenes\rol_calle.png' height = 400>
<p>


## Franja Horaria

- En general, el rango de las 6 a las 9 de la mañana muestra un nivel elevado de víctimas fatales, alrededor del 17% de las muertes.
- Durante los fines de semana, es decir, los días sábados y domingos, el porcentaje de víctimas fatales en el rango de 3 a 9 de la mañana es notablemente alto. Los domingos, este porcentaje alcanza un preocupante 50% del total de víctimas fatales, mientras que los sábados muestran un 46%.
- Además el promedio de muertes en general aumenta considerablemente en la madrugada y primeras horas del día.
<p align='center'>
<img src = 'imagenes\franja_horaria_.png' height = 500>
<p>


## KPI (Indicadores Clave de Rendimiento)

Se plantearon tres objetivos en relación a la disminución de la cantidad de víctimas fatales de los siniestros viales, desde los cuales se proponen tres indicadores de rendimiento clave o KPI.

**KPI 1 - Tasa de Homicidios en Siniestros Viales:**
- Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región.
- Se define como Tasa de homicidios en siniestros viales al número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico (en este caso, 6 meses).

**KPI 2 - Accidentes Mortales de Motociclistas:**
- Dado que el 42% de las víctimas mortales se transportaban en moto, se consideró importante monitorear la cantidad de accidentes mortales en este tipo de conductor.
- La fórmula para medir la evolución de los accidentes mortales con víctimas en moto compara el número de accidentes mortales entre el año anterior y el actual.

**KPI 3 - Tasa de Homicidios en Avenidas:**
- Dado que el 62% de las víctimas mortales transitaban por avenidas, se planteó reducir la tasa de homicidios en este contexto.
- La Tasa de homicidios en avenidas se calcula como el número de homicidios en accidentes en avenidas por cada 100,000 habitantes en un área geográfica durante un año.

<p align='center'>
<img src = 'imagenes\KPI.png' height = 400>
<p>


# Conclusiones y Recomendaciones

- Se registraron 717 víctimas fatales en siniestros viales entre 2016 y 2021 en CABA.

- Se observa una leve tendencia a la baja, sobre todo desde 2019 en adelante

- KPI 1: Para el segundo semestre de 2021, se cumplió con el objetivo de reducir la tasa de homicidios en siniestros viales.
- KPI 2: Lamentablemente, para el año 2021, se observó un aumento del 64% en la cantidad de accidentes mortales de motociclistas respecto del año 2020 y no se logró alcanzar el objetivo de reducción en un 7%.
- KPI 3: Para el año 2021, no se cumplió con el objetivo de reducir la tasa de homicidios en avenidas, ya que esta aumentó en comparación con el año anterior.

- Se recomienda continuar monitoreando y reforzar las campañas de seguridad vial, especialmente dirigidas a conductores de motos y usuarios de avenidas, en días específicos y en el mes de diciembre. 

- Al analizar la distribución de víctimas fatales en función de la franja horaria, hemos identificado un patrón significativo que merece atención.
Este análisis resalta la importancia de considerar no solo la franja de las 6 a las 9 de la mañana en general, sino también la incidencia significativamente alta de accidentes los fines de semana en el rango de 3 a 9 de la mañana. Estos hallazgos pueden proporcionar valiosa información para orientar futuras estrategias de prevención de accidentes viales en la ciudad.

- La cantidad de peatones muertos resultado de siniestros viales es considerablemente alta y es la segunda víctima despues de los motociclistas. La mayoría de las muertes de peatones son provocadas por vehículos de transporte de pasajeros, lo cual se recomienda poner énfasis en este punto.

Este informe proporciona una visión completa de la metodología, el preprocesamiento de datos y los resultados del análisis de homicidios en siniestros viales en la Ciudad Autónoma de Buenos Aires. Los hallazgos y visualizaciones presentadas son fundamentales para abordar y mejorar la seguridad vial en la ciudad.
