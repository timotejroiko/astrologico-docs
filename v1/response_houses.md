## Houses

The houses field contains the calculated data for all the house cusps and angles using the house system specified in [Houses](parameters_houses.md) as well as several other horizontal points.

| Value | Type | Descripton |
|---|---|---|
| [houses](#house) | Object | Object containing house cusps data |
| [ascendant](response_data.md) | Object | Ascendant |
| [mc](response_data.md) | Object | MC (midheaven / medium coeli) |
| [ramc](response_data.md) | Object | ARMC (right rscencion of the midheaven) |
| [vertex](response_data.md) | Object | Vertex |
| [equatorialAscendant](response_data.md) | Object | Equatorial Ascendant |
| [kochCoAscendant](response_data.md) | Object | Koch co-Ascendant |
| [munkaseyCoAscendant](response_data.md) | Object | Munkasey co-Ascendant |
| [munkaseyPolarAscendant](response_data.md) | Object | Munkasey Polar Ascendant |
| [descendant](response_data.md) | Object | Descendant |
| [ic](response_data.md) | Object | Imum Coeli |
| [antiVertex](response_data.md) | Object | Anti-Vertex |
| [zenith](response_data.md) | Object | Zenith |
| [nadir](response_data.md) | Object | Nadir |
| [northPoint](response_data.md) | Object | North Point |
| [eastPoint](response_data.md) | Object | East Point |
| [southPoint](response_data.md) | Object | South Point |
| [westPoint](response_data.md) | Object | West Point |
| [northPole](response_data.md) | Object | North Pole |
| [southPole](response_data.md) | Object | South Pole |
| error | String | error message* |

\* If an error occurs, an error message is displayed here and no other fields are returned.

<br>

### Houses - House

The inner houses field contains the calculated house cusps for the selected house system. When using Gauquelin Sectors the number of house cusps returned is 36 instead of 12, and the house cusps are clockwise instead of counterclockwise.

| Value | Type | Descripton |
|---|---|---|
| [house1](response_data.md) | Object | 1st house |
| [house2](response_data.md) | Object | 2nd house |
| [house3](response_data.md) | Object | 3rd house |
| ... | Object | etc... |

<br>