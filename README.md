# Homicidios en USA 

### Temática del Proyecto  – Homicidios en Estados Unidos

## Author

- [@Ewapls](https://github.com/Ewapls)

1.  ### Objetivo
El objetivo de este análisis es poder comprender la problemática de homicidios en Estados Unidos y proporcionar insights valiosos para la formulación de estrategias preventivas y de gestión. A través del análisis de datos rigurosos, buscaremos identificar relaciones causales, patrones estacionales, y cualquier otro elemento que contribuya a comprender mejor la dinámica de los homicidios en el país.

2.	### Alcance
El dataset utilizado contiene 139701 filas y 10 columnas, abarca los homicidios ocurridos en Estados Unidos entre el 01/01/2006 al 28/12/2014.

3.	### Usuario Final y Nivel de Aplicación del Análisis (Operativo, Tactico y Estrategico)
Usuario Final: serían usuarios tácticos que orientan al usuario en el camino de la toma de decisiones a medio plazo. Los usuarios podrían incluir analistas de crímenes, jefes de policías o planificadores de seguridad.

Nivel de Aplicación del Análisis: Táctico en el cual se proporciona informes detallados sobre análisis del modus operandi, áreas de mayor riesgo, relaciones en los homicidios y grupos demográficos afectados. Pueden permitir que los usuarios exploren estos datos de manera profunda permitiéndoles obtener información relevante para la planificación táctica.

4.	### Diagrama entidad-relación 
A continuación, se detalla el diagrama entidad-relación creado: 

![DER](/images/DER.png/)


5.	### Listado de Tablas
En este apartado, se mencionará cada una de las tablas junto a una breve descripción de las mismas y la definición de la clave primaria y foránea:

●	Homicidios: contiene la cantidad de homicidios, agencias, localización, fecha, tipo de homicidio, estado del crimen, datos de las víctimas y victimarios, relación de los involucrados en el homicidio y la fuente de donde se obtiene la data.
-	PK: Record_ID
-	FK: ID_ Agency
-	FK: ID_Location
-	FK: ID_Crime
-	FK: ID_Victim
-	FK: ID_Perpetrator
-	FK: ID_Relationship

●	Agencias: contiene las agencias registradas, el nombre de estas y el tipo.
-	PK: ID_Agency
-	: Agency_Name
-	: Agency_Type

●	Ubicación: contiene las ubicaciones registradas, ciudad y estado.
-	PK: ID_Location
-	 : City
-	 : State

●	Tipo de Homicidio: contiene el tipo de crimen y el arma con el que se perpetuo.
-	PK: ID_Crime
-	: Crime_Type
-	: Weapon

●	Victimas: contiene el sexo de la victima, edad, raza, identidad etnica y contador adicional de victimas.
-	PK: ID_Victim
-	: Victim_Sex
-	: Victim_Age
-	: Victim_Race
-	: Victim_ethnicity
-	: Victim_Count_Addition

●	Victimario: contiene contador de reincidentes (reincidencia en crimenes), sexo del perpetrador, edad, raza, identidad etnica y recuento de perpetradores (que participaron en el incidente).
-	PK: ID_Perpetrator
-	: Incident 
-	: Perpetrator_sex
-	: Perpetrator_age
-	: Perpetrator_ race
-	: Perpetrator_ethnicity
-	: Perpetrator_count

●	Relación: contiene su indicador para cada tipo de relación (víctima al agresor).
-	 PK: ID_Relationship
-	 : relationship 

6.	### Listado de Columnas por Tablas
A continuación, se mencionará las columnas que posee cada tabla junto con su tipo de campo y clave.

#### Tabla Homicidios
| Campo |  Tipo de dato  | Tipo de Clave |
|:-----|:--------:|------:|
| Record_ID   | int | PK - Index |
| ID_Agency  |  varchar  |   FK |
| ID_Location   | varchar |    FK |
| Date   |  date  |   - |
| ID_Crime   | varchar |    FK |
| Crime_Solve   |  boolean  |   - |
| ID_Victim   | varchar |    FK |
| ID_Perpetrator   |  varchar  |   $12 |
| ID_Relationship   | varchar |    FK |
| Record Source   |  varchar  |   - |

#### Tabla Agencias
| Campo |  Tipo de dato  | Tipo de Clave |
|:-----|:--------:|------:|
| ID_Agency   | varchar | PK |
| Agency_Name  |  varchar  |   - |
| Agency Type   | varchar |    - |

#### Tabla Ubicacion
| Campo |  Tipo de dato  | Tipo de Clave |
|:-----|:--------:|------:|
| ID_Location   | varchar | PK |
| City  |  varchar  |   - |
| State   | varchar |    - |

#### Tabla Tipos de Homicidios
| Campo |  Tipo de dato  | Tipo de Clave |
|:-----|:--------:|------:|
| ID_Crime   | varchar | PK |
| Crime Type  |  varchar  |   - |
| Weapon   | varchar |    - |

#### Tabla Victimas
| Campo |  Tipo de dato  | Tipo de Clave |
|:-----|:--------:|------:|
| ID_Victim   | varchar | PK |
| Victim Sex  |  varchar  |   - |
| Victim Age   | int |    - |
| Victim Rage   |  varchar  |   - |
| Victim Ethnicity   | varchar |   - |
| Victim Count Addition   |  int  |   - |

#### Tabla Victimario
| Campo |  Tipo de dato  | Tipo de Clave |
|:-----|:--------:|------:|
| ID_Perpetrator   | varchar | PK |
| Incident  |  int  |   - |
| Perpetrator Sex   | varchar |    - |
| Perpetrator Age   |  int  |   - |
| Perpetrator Race   | varchar |   - |
| Perpetrator Ethnicity   |  varchar  |   - |
| Perpetrator Count   |  int  |   - |

#### Tabla Relacion
| Campo |  Tipo de dato  | Tipo de Clave |
|:-----|:--------:|------:|
| ID_Relationship   | varchar | PK |
| Relationship  |  varchar  |   - |

7.	### Transformaciones Realizadas 
Este  Dataset fue brindado por el docente del curso el cual nos brinda datos sobre homicidios en el país de los Estados Unidos. Básicamente hay 1 dataset  principal, en el cual posteriormente creamos nuestras tabla de hecho y sacamos las tablas de dimensiones. Todo el dataset está en formato XLSX, y tienen un peso de 18.3 MB. Dicho esto, todo el proceso ETL se realizó con Power Query.

- A.	Tabla Homicidios_hechos
En el dataset relacionado con los homicidios realizamos el siguiente proceso ETL.

![Homicidios_hechos](/images/t_homicidios_hechos1.png/)



![Agencias](/images/transformacion_2.png/)



![Relacion_Victima_Victimario](/images/transformacion_3.png/)



![Tipos_de_Homicidios](/images/transformacion_4.png/)



![ubicacion](/images/transformacion_5.png/)



![victimario](/images/transformacion_6.png/)



![victimas](/images/transformacion_7.png/)


8.	### Medidas calculadas con fórmulas
Se crearon 9 medidas calculadas en esta carpeta llamada “Homicidios”. Todas fueron ordenadas dentro de una carpeta llamada “DAX Medidas”.


![dax_homicidios](/images/homicidios_dax_8.png/)


A continuación, se detalla como se calculó cada medida y que finalidad tiene cada una de ellas. 

***
#### Medida: Homicidio por Estado Promedio Homicidio por Estado
Promedio = 

VAR _Homicidios = [Homicidios Totales] VAR _HomicidiosPorEstado = DISTINCTCOUNT(dim_ubicacion[State])

RETURN

DIVIDE(_Homicidios,_HomicidiosPorEstado)

Finalidad: Esta medida es una división de otras 2 medidas creadas previamente. Se utiliza para tener el promedio de homicidios por estado.
***
#### Medida: Homicidios por ciudad promedio
Homicidios por Ciudad Promedio =

VAR _Homicidios = [Homicidios Totales]
VAR _RecuentoHomicidiosCity = COUNTROWS(dim_ubicacion)

RETURN

DIVIDE(_Homicidios, _RecuentoHomicidiosCity)

Finalidad: Esta medida es una división de otras 2 medidas creadas previamente. Se utiliza para tener el promedio de homicidios por ciudad.
***
#### Medida: Homicidios Totales

Homicidios Totales =

COUNTROWS(
    FILTER(
        Homicidios Hechos,
        NOT(ISBLANK(Homicidios_hechos[Homicidios Sexo]))
    )
)

Finalidad: Esta medida nos arroja la cantidad totales de homicidios pero filtrando los campo en blanco de columna “Homicidios Sexo”.
***
#### Medida: Homicidios Totales Año Anterior

Homicidios Totales Año Anterior =

CALCULATE([Homicidios Totales], DATEADD(dim_Calendario[Fecha], -1, YEAR))

Finalidad: Esta medida nos arroja la cantidad de homicidios hasta el año anterior con respecto a nuestro último año con datos de homicidios. Es decir, nuestro último año es el 2014 pero esta fórmula nos brinda la suma de homicidios hasta el año 2013.
Medida: Homicidios Victimas Female Numeros
***
#### Medida: Homicidios Victimas Female Numeros

Homicidios Victimas Female Numeros =
COUNTROWS(
    FILTER(
        Homicidios_hechos,
        Homicidios_hechos[Homicidios Sexo] = "Female"
    )
)

Finalidad: Esta medida nos arroja la cantidad total de victimas del sexo femenino en los homicidios. La medida está formateada en un número entero.
***
#### Medida: Homicidios Victimas Female  en porcentaje

Homicidios Victimas Female en porcentaje =
(COUNTROWS(
    FILTER(
        Homicidios_hechos,
        Homicidios_hechos[Homicidios Sexo] = "Female"
    )
)) / [Homicidios Totales]

Finalidad: Esta medida es dividida entre otra calculada previamente. Nos da la cantidad victimas del sexo femenino en numero de porcentaje con respecto al total de homicidios.
***
#### Medida: Homicidios Victimas Male Numeros

Homicidios Victimas Male Numeros =
COUNTROWS(
    FILTER(
        Homicidios_hechos,
        Homicidios_hechos[Homicidios Sexo] = "Male"
    )
)

Finalidad: Esta medida nos arroja la cantidad total de victimas del sexo masculino en los homicidios. La medida está formateada en un número entero.
***
#### Medida: Homicidios Victimas Female  en porcentaje

Homicidios Victimas Male en porcentaje =
(COUNTROWS(
    FILTER(
        Homicidios_hechos,
        Homicidios_hechos[Homicidios Sexo] = "Male"
    )
)) / [Homicidios Totales]

Finalidad: Esta medida es dividida entre otra calculada previamente. Nos da la cantidad victimas del sexo masculino en numero de porcentaje con respecto al total de homicidios.
***
#### Medida: Titulo ToolTip

Titulo ToolTip =

VAR _Anio = SELECTEDVALUE(dim_Calendario[Año])
VAR _Bimestre = SELECTEDVALUE(dim_Calendario[Bimestre Nombre])

RETURN

"Visualizando el periodo " & _Anio & " - " & _Bimestre

Finalidad: Esta medida nos servirá como tooltip para una apreciar mejor los puntos en una visualización.
***

#### Más medidas DAX
Se crearon 7 medidas calculadas para la página de conclusiones. Todas fueron ordenadas dentro de una carpeta llamada “DAX Medidas”.

![dax_mas_medidas](/images/dax_9.png/)

***
#### Medida: Cuartil 1

Cuartil 1 = PERCENTILE.INC('Homicidios Agrupado'[Numero Homicidios Agrupados], 0.25)

Finalidad: Esta medida es creada para saber el valor que corresponde al 25% de toda la distribución en la columna ‘Número Homicidios Agrupados’.
***
#### Medida: Cuartil 3

Cuartil 3 = PERCENTILE.INC('Homicidios Agrupado'[Numero Homicidios Agrupados], 0.75)

Finalidad: Esta medida es creada para saber el valor que corresponde al 75% de toda la distribución en la columna ‘Número Homicidios Agrupados’.
***
#### Medida: Homicidio más frecuente por ciudad

Homicidio mas frencuente por ciudad = TOPN(1, SUMMARIZE(Homicidios_hechos, dim_ubicacion[City_State]), [Homicidios Totales], DESC))

Finalidad: Esta medida se creará para saber cual es el valor mas frecuente que ha salido de la columna ‘Homicidios totales’ de la tabla virtual creada con SUMMARIZE.
***
#### Medida: Homicidio Mediana por ciudad MTC

Homicidio Mediana por Ciudad MTC = MEDIAN('Homicidios Agrupado'[Numero Homicidios Agrupados])

Finalidad: Esta medida me permite saber el valor que está justo en el medio de toda la distribución de valores de la columna ‘Numero Homicidios Agrupados’.
***
#### Medida: Homicidios Moda Frecuencia por ciudad MTC

Homicidios Moda Frecuencia por ciudad MTC =

VAR _Tabla_Agrupada = SUMMARIZE('Homicidios Agrupado', 'Homicidios Agrupado'[Numero Homicidios Agrupados], "Recuento", COUNTROWS('Homicidios Agrupado'))
VAR _Maximo = MAXX(_Tabla_Agrupada, [Recuento])

RETURN

_Maximo

Finalidad: Esta medida me permite saber el valor que está justo en el medio de toda la distribución de valores de la columna ‘Numero Homicidios Agrupados’.
***
9.	### Conclusiones y Futuras Lineas
Se logro ver en el analisis el comportamiento a rasgos generales y específicos con el uso de segmentadores sobre los homicidios en general en estados unidos, pudiendo encontrar patronos y tendencias gracias a nuestro analisis.
Ademas, se pudo crear visualizaciones que nos ayudaron a ver todos estos patrones y tendencias de manera muy intuitiva y llevar estos analisis a la aplicacion en el toma de decisiones de los insights obtenidos para poder plantear tacticas por parte de agencias policiales, planificadores de seguridad y otros actores involucrados en la gestión de la violencia.
Finalmente, se pudo corroborar muchos datos como que el estados de California es el que mas homicidios se han llevado a cabo, pudimos ver como estos homicidios se comportaban en el paso del tiempo, pudimos usar segmentadores para ver patrones en las victimas y victimarios, incluso analizando de forma separada cada uno de estos para un analisis mas profundo, por ultimo creamos una seccion para ver datos estadisticos como la moda, media, percentilides de la distribucion de datos y mucho mas.
