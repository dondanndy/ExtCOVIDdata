# COVID data in Extremadura

This repository collects the data of COVID cases in Extremadura provided by the regional government for each population unit in the region.

In addition to the daily data, case notification rates from previous days is also calculated and provided.

## File structure

In the `raw` folder it is possible to find the original `pdf` files provided by the regional government.

In the folder `csv` it is possible to find the `csv` files generated from the original files.

The `pdf` files from the regional government contain a large number of spelling errors in the names of towns/provinces/health zones, as well as being inconsistent on several occasions, with errors in the presentation of data - such as repetition of some towns on the same day-.

These errors have been fixed (as far as possible) in the `csv` files, in order to make it easier to automate the analysis of the data.

Finally, the `munDATA` folder contains the inhabitant numbers for every population unit in Extremadura, extracted from the [Spanish National Institute of Statistics (INE)](https://www.ine.es/nomen2/index.do) figures from 2019, the most recent data available.

In addition to the data provided by the INE, the population of [Valdelamantanza](https://es.wikipedia.org/wiki/Valdelamatanza) is included in the province of Cáceres. Although it belongs to the province of Salamanca, the regional government includes it in the reports because there is an agreement in place for health matters.

## Data file

The file `data.csv` holds the collection of daily and accumulated cases from every population unit in Extremadura.

It is important to highlight that these are not values per municipality, but per population unit, the same way the regional government provides this data.

This file is conceived with the structure of a DataFrame, present in several libraries for different programming languages.

Its structure contains the following values:
| Value  | Description |
|:-:|:-:|
| day | Day which the data is referring to. The regional government reports the cases from the previous day, so that date is also used here. For example, the data reported on October 2nd appears with `2020-10-01`.  |
| location  | Population unit, with the name given by INE. |
| cases  | Notified cases on the specified day. |
| cases7  | 7-day case notification aggregation. |
| IA7  | 7-day case notification rate per 100 000 inhabitants. |
| cases14  | 14-day case notification aggregation.  |
| IA14  | 14-day case notification rate per 100 000 inhabitants. |

Values of case aggregation and case rate will be `-1` on the first days of the collection, as there is not enough data to calculate them.

Also, the 7-day and 14-day case rate will also take that value in the case of the _Monfragüe_ population unit, which the regional government mentions in one of the reports but for which no population data is available.

# Licence

The original data was published by the Junta de Extremadura (Extremadura regional government) and the Spanish National Institute of Statistics.

The subsequent work made on them lies on the public domain.
