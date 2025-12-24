Información sobre el data set

| column               | translate                                           | dtype           | null_pct | example_value        |
|----------------------|-----------------------------------------------------|-----------------|----------|----------------------|
| year                 | Año                                                 | Int64           | 0        | 2024                 |
| month                | Mes                                                 | Int64           | 0        | 1                    |
| day_of_month         | Día del mes                                         | Int64           | 0        | 1                    |
| day_of_week          | Día de la semana                                    | Int64           | 0        | 1                    |
| fl_date              | Fecha del vuelo                                     | datetime64[ns]  | 0        | 01/01/2024 00:00     |
| op_unique_carrier    | Código único que identifica aerolínea               | object          | 0        | 9E                   |
| op_carrier_fl_num    | Número de vuelo                                     | float64         | 0        | 4814                 |
| origin               | Origen del vuelo                                    | object          | 0        | JFK                  |
| origin_city_name     | Ciudad donde se origina el despegue                 | object          | 0        | New York, NY         |
| origin_state_nm      | Estado                                              | object          | 0        | New York             |
| dest                 | Destino                                             | object          | 0        | DTW                  |
| dest_city_name       | Ciudad destino                                      | object          | 0        | Detroit, MI          |
| dest_state_nm        | Estado destino                                      | object          | 0        | Michigan             |
| crs_dep_time         | Hora programada para el despegue                    | Int64           | 0        | 1252                 |
| dep_time             | Hora real de despegue                               | float64         | 1.31     | 1247                 |
| dep_delay            | Retraso en la hora de despegue                      | float64         | 1.31     | -5                   |
| taxi_out             | Recorrido por la pista mientras despega             | float64         | 1.35     | 31                   |
| wheels_off           | Momento en que el avión termina recorrido y despega | float64         | 1.35     | 1318                 |
| wheels_on            | Momento en que el avión inicia recorrido al aterrizar| float64        | 1.38     | 1442                 |
| taxi_in              | Recorrido por la pista durante el aterrizaje        | float64         | 1.38     | 7                    |
| crs_arr_time         | Horario programado para aterrizaje                  | Int64           | 0        | 1508                 |
| arr_time             | Hora real de llegada del vuelo                      | float64         | 1.38     | 1449                 |
| arr_delay            | Retraso de llegada del vuelo                        | float64         | 1.61     | -19                  |
| cancelled            | Vuelo cancelado                                     | int64           | 0        | 0                    |
| cancellation_code    | Código de cancelación                               | object          | 98.64    | B                    |
| diverted             | Cambio de ruta durante el vuelo                     | int64           | 0        | 0                    |
| crs_elapsed_time     | Tiempo programado del trayecto                      | float64         | 0        | 136                  |
| actual_elapsed_time  | Tiempo total del trayecto                           | float64         | 1.61     | 122                  |
| air_time             | Tiempo de vuelo                                     | float64         | 1.61     | 84                   |
| distance             | Distancia                                           | float64         | 0        | 509                  |
| carrier_delay        | Retraso de aerolínea                                | int64           | 0        | 0                    |
| weather_delay        | Retrasos por clima                                  | int64           | 0        | 0                    |
| nas_delay            | Retraso por gestión del espacio aéreo               | int64           | 0        | 0                    |
| security_delay       | Retraso por controles de seguridad                  | int64           | 0        | 0                    |
| late_aircraft_delay  | Retraso por vuelos anteriores del avión             | int64           | 0        | 0                    |
