## Houses

This parameter enables Houses and sets a House System with which to calculate Houses, Ascendant, Midheaven and other related points. It also supports calculating houses from a specific RAMC (Right Ascension of the Midheaven) value, such as for obtaining composite houses.

| Index | Type | Descripton |
|---|---|---|
| 0 | Integer | House System ID (required) |
| 1 | Float | RAMC value \* |
| 2 | Float | Obliquity value \* |

\* If index 1 and 2 are set, the houses will be calculated from the given RAMC value instead of the date and location (it still requires a geographic location to be set). Calculating houses from an RAMC also requires specifying the Obliquity of the ecliptic value and is only available in the [Chart](endpoints_chart.md) Endpoint.

<br>

### Houses - House System IDs

| ID | House System |
|---|---|
| 1 | Alcabitus |
| 2 | APC |
| 3 | Axial Rotation / Meridian / Zariel |
| 4 | Azimuthal / Horizontal |
| 5 | Campanus |
| 6 | Carter / Poli-Equatorial |
| 7 | Equal (1st house = ascendant) |
| 8 | Equal (10th house = midheaven) |
| 9 | Equal (1st house = 0 aries) |
| 10 | Gauquelin Sectors |
| 11 | Sunshine / Makransky (solution Treindl) |
| 12 | Sunshine / Makransky (solution Makransky) |
| 13 | Koch |
| 14 | Krusinski / Pisa / Goelzer |
| 15 | Morinus |
| 16 | Placidus |
| 17 | Polich / Page / Topocentric |
| 18 | Porphyry |
| 19 | Pullen SD (sinusoidal delta) / Neo-Porphyry |
| 20 | Pullen SR (sinusoidal ratio) |
| 21 | Regiomontanus |
| 22 | Sripati |
| 23 | Vehlow Equal (middle of 1st house = ascendant) |
| 24 | Whole Sign |

<br>

### Example

Retrieving houses, Ascendant, Midheaven and other related points using the `Placidus` house system.

| GET | POST |
|---|---|
|houses=16|houses:[16]|

Retrieving houses, Ascendant, Midheaven and other related points using the `Placidus` house system for a "Composite" chart. This calculation requires 3 values: The average RAMC from the combined charts, the average Obliquity of the Ecliptic from the combined charts and the average Geographic Latitude from the combined charts (ie: location=35|0). Some values might not be available here.

| GET | POST |
|---|---|
|houses=16\|225.325\|23.546|houses:[16,225.325,23.546]|

<br>