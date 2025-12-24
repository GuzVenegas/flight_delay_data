# Información de las variables:


| column               | Description                                      | Description (translate)                                      | var_type            | dtype           | null_pct | example_value        |
|----------------------|--------------------------------------------------|--------------------------------------------------------------|---------------------|-----------------|----------|----------------------|
| year                 | Year of flight                                   | Año                                                          | numérica-discreta   | Int64           | 0        | 2024                 |
| month                | Month of flight (1–12)                           | Mes                                                          | numérica-discreta   | Int64           | 0        | 1                    |
| day_of_month         | Day of the month                                 | Día del mes                                                  | numérica-discreta   | Int64           | 0        | 1                    |
| day_of_week          | Day of week (1=Monday … 7=Sunday)                | Día de la semana                                             | numérica-discreta   | Int64           | 0        | 1                    |
| fl_date              | Flight date (YYYY-MM-DD)                         | Fecha del vuelo                                              | numérica-discreta   | datetime64[ns]  | 0        | 01/01/2024 00:00     |
| op_unique_carrier    | Unique carrier code                              | Código único que identifica aerolínea                        | categórica          | object          | 0        | 9E                   |
| op_carrier_fl_num    | Flight number for reporting airline              | Número de vuelo                                              | numérica-discreta   | float64         | 0        | 4814                 |
| origin               | Origin airport code                              | Origen del vuelo                                             | categórica          | object          | 0        | JFK                  |
| origin_city_name     | Origin city name                                 | Ciudad donde se origina el despegue                          | categórica          | object          | 0        | New York, NY         |
| origin_state_nm      | Origin state name                                | Estado                                                       | categórica          | object          | 0        | New York             |
| dest                 | Destination airport code                         | Destino                                                      | categórica          | object          | 0        | DTW                  |
| dest_city_name       | Destination city name                            | Ciudad destino                                               | categórica          | object          | 0        | Detroit, MI          |
| dest_state_nm        | Destination state name                           | Estado destino                                               | categórica          | object          | 0        | Michigan             |
| crs_dep_time         | Scheduled departure time (local, hhmm)           | Hora programada para el despegue                             | numérica-continua   | Int64           | 0        | 1252                 |
| dep_time             | Actual departure time (local, hhmm)              | Hora real de despegue                                        | numérica-continua   | float64         | 1.31     | 1247                 |
| dep_delay            | Departure delay in minutes (negative if early)   | Retraso en la hora de despegue                               | numérica-continua   | float64         | 1.31     | -5                   |
| taxi_out             | Taxi out time in minutes                         | Recorrido por la pista mientras despega                      | numérica-continua   | float64         | 1.35     | 31                   |
| wheels_off           | Wheels-off time (local, hhmm)                    | Momento en el que el avión termina recorrido y despega       | numérica-continua   | float64         | 1.35     | 1318                 |
| wheels_on            | Wheels-on time (local, hhmm)                     | Momento en el que el avión comienza recorrido al aterrizar   | numérica-continua   | float64         | 1.38     | 1442                 |
| taxi_in              | Taxi in time in minutes                          | Recorrido por la pista durante el aterrizaje                 | numérica-continua   | float64         | 1.38     | 7                    |
| crs_arr_time         | Scheduled arrival time (local, hhmm)             | Horario programado para aterrizaje                           | numérica-continua   | Int64           | 0        | 1508                 |
| arr_time             | Actual arrival time (local, hhmm)                | Hora real de llegada del vuelo                               | numérica-continua   | float64         | 1.38     | 1449                 |
| arr_delay            | Arrival delay in minutes (negative if early)     | Retraso de llegada del vuelo                                 | numérica-continua   | float64         | 1.61     | -19                  |
| cancelled            | Cancelled flight indicator (0=No, 1=Yes)         | Vuelo cancelado                                              | boolean             | int64           | 0        | 0                    |
| cancellation_code    | Reason for cancellation (if cancelled)           | Código de cancelación                                        | categórica          | object          | 98.64    | B                    |
| diverted             | Diverted flight indicator (0=No, 1=Yes)          | Cambio de ruta durante el vuelo                              | boolean             | int64           | 0        | 0                    |
| crs_elapsed_time     | Scheduled elapsed time in minutes                | Tiempo programado del trayecto                               | numérica-continua   | float64         | 0        | 136                  |
| actual_elapsed_time  | Actual elapsed time in minutes                   | Tiempo total del trayecto                                    | numérica-continua   | float64         | 1.61     | 122                  |
| air_time             | Flight time in minutes                           | Tiempo de vuelo                                              | numérica-continua   | float64         | 1.61     | 84                   |
| distance             | Distance between origin and destination (miles)  | Distancia                                                    | numérica-continua   | float64         | 0        | 509                  |
| carrier_delay        | Carrier-related delay in minutes                 | Retraso de aerolínea                                         | numérica-continua   | int64           | 0        | 0                    |
| weather_delay        | Weather-related delay in minutes                 | Retrasos por clima                                           | numérica-continua   | int64           | 0        | 0                    |
| nas_delay            | National Air System delay in minutes             | Retraso por gestión del espacio aéreo                        | numérica-continua   | int64           | 0        | 0                    |
| security_delay       | Security delay in minutes                        | Retraso por controles de seguridad                           | numérica-continua   | int64           | 0        | 0                    |
| late_aircraft_delay  | Late aircraft delay in minutes                   | Retraso por vuelos pasados                                   | numérica-continua   | int64           | 0        | 0                    |


# Consideraciones iniciales del análisis exploratorio de datos (EDA)

En el conjunto de datos se identificaron valores nulos. Para facilitar su manejo, se calculó la proporción de datos faltantes en cada variable. En este sentido, la variable **`cancellation_code`** presenta un **98.64% de valores nulos**, por lo que se decidió eliminarla.  
Adicionalmente, se consideró retirar las variables **`cancelled`** y **`year`** en la etapa inicial del análisis.

---

## Variables con valores nulos

Además de `cancellation_code`, se contabilizaron **12 variables con valores nulos**.  
Este subconjunto se denominó **`missing_values`**. En dichas variables, la proporción de valores nulos no supera el **2%**, lo que plantea la siguiente pregunta:

> **¿Qué tipo de imputación estadística es más adecuada para completar estos valores nulos en el dataset?**

---

## Propuestas de imputación

### 1. Métodos básicos
- **Visualizaciones**: analizar la distribución de las variables numéricas continuas antes de decidir la imputación.  
- **Moda**: útil para variables categóricas.  
- **Moda en numéricas discretas**: puede ser considerada como alternativa.

### 2. Métodos avanzados
- **Regresión lineal**: estimar valores faltantes a partir de relaciones con otras variables.  
- **KNN Imputer**: imputación basada en vecinos más cercanos.

### 3. Métodos basados en reglas
- **Imputación condicional**: usar medidas estadísticas por grupo (ej. por aerolínea o mes).  
- **Valores constantes**: asignar un valor fijo (ej. 0 en retrasos).  
- **Forward/Backward fill**: rellenar con valores anteriores o posteriores en series temporales.

---



