# Datos de COVID en Extremadura

[*You can read this README in English by clicking in this link.*](https://www.github.com/dondanndy/ExtCOVIDdata/README_EN.md)

En este repositorio se recogen los datos de casos de COVID proporcionados por al Junta de Extremadura para cada núcleo de población.

Además de los datos de cada día por separado, también figuran los datos de incidencia acumulada calculada a partir de ellos.

## Estructura de archivos

En la carpeta `raw` es posible encontrar los archivos `pdf` originales proporcionados por la Junta de Extremadura.

En la carpeta `csv` es posible encontrar los archivos `csv` generados a partir de los archivos originales.

Cabe destacar que los archivos en `pdf` proporcionados por la Junta contienen un gran número de errores ortográficos en los nombres de las poblaciones/provincias/zonas de salud, además de ser inconsistentes en varias ocasiones, con errores a la hora de presentar los datos --como por ejemplo repetición de algunas poblaciones--.

En los archivos `csv` se han intentado corregir todos estos errores en la medida de lo posible, para también facilitar la automatización de su análisis.

Por último en la carpeta `munDATA` figuran los datos de población de las unidades poblacionales de Extremadura, extraídos de datos del [Instituto Nacional de Estadística (INE)](https://www.ine.es/nomen2/index.do) del 2019, fecha más actualizada.

Además de los datos proporcionados por el INE, también figura, en la provicia de Cáceres, la población de [Valdelamantanza](https://es.wikipedia.org/wiki/Valdelamatanza). Aunque pertenezca a la provincia de Salamanca, la Junta la incluye en los informes por tener un acuerdo en materia de salud.

## Archivo de datos

En el archivo `data.csv` figura la recopilación de casos e incidencias de todas las unidades poblacionales de Extremadura.

Es importante destacar que no se trata de valores por municipios, sino por unidades poblacionales, tal y como la Junta proporciona estos datos.

Dicho archivo está concebido con la estructura de un DataFrame, presente en varias librerías para diversos lenguajes de programación.

Sus valores son:
| Valor  | Concepto |
|:-:|:-:|
| day | Día para el que figuran los datos. En los informes de la Junta se publican los casos notificados el día previo, así que se indica de la misma manera en el archivo de datos. Por ejemplo, los datos proporcionados el 2 de octubre aparecen con la fecha `2020-10-01`.  |
| location  | Unidad poblacional referida, con el nombre dado por el INE.  |
| cases  | Casos notificados el día indicado.  |
| cases7  | Suma de los casos notificados los 7 días anteriores, incluyendo el día indicado.  |
| IA7  | Incidencia acumulada de 7 días, es decir, la suma de los casos de los 7 días anteriores al indicado por 100.000 habitantes.  |
| cases14  | Suma de los casos notificados los 14 días anteriores, incluyendo el día indicado.  |
| IA14  | Incidencia acumulada de 14 días, es decir, la suma de los casos de los 14 días anteriores al indicado por 100.000 habitantes.  |

Los valores de casos e incidencia acumulada toman el valor de `-1` los primeros días de la serie, donde no hay datos durante el suficiente número de días para obtenerlos.

Además, los datos de incidencia acumulada también tomarán ese valor en el caso de la unidad de población de Monfragüe, que la Junta indica en uno de los reportes pero para la que no figuran datos de población.

# Licencia

Los datos originales han sido hechos públicos por la Junta de Extremadura y el Instituto Nacional de Estadística.

El trabajo posterior realizado sobre ellos queda en el dominio público.