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

![Homicidios_hechos](/images/transformacion_1.png/)
