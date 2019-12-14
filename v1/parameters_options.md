## Options

An array of options to configure several chart generation settings, timezones, etc...

| option | Descripton |
|---|---|
| TRUEPOSITIONS | Return True positions instead of Apparent |
| HELIOCENTRIC | Return Heliocentric positions instead of Geocentric |
| TOPOCENTRIC | Return Topocentric positions instead of Geocentric |
| ASTROMETRIC | Astrometric positions (disable Aberration of Light and Gravitational Deflection) |
| JULIAN | Use Julian calendar instead of automatic |
| GREGORIAN | Use Gregorian calendar instead of automatic |
| UTCTOLOCAL | Convert UTC date to Local Date when input is in UTC (increases total cost by 2) |
| USAGE | Return information about your key's current usage, rate limits, expiration, etc... |

Using the option `UTCTOLOCAL` increases the request's total cost by 2.

<br>

### Example

Create a heliocentric chart with true astrometric positions

| GET | POST |
|---|---|
|options=TRUEPOSITIONS\|ASTROMETRIC\|HELIOCENTRIC|options:["TRUEPOSITIONS","ASTROMETRIC","HELIOCENTRIC"]|

<br>