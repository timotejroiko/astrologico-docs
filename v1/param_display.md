## Display

An array of planetary values the request should return. If none is specified, it defaults to `LONGITUDE LONGITUDE_SPEED`. Not all objects support all display values, for more info see [Response Data](/astrologico/res_data.html);

| option | Descripton |
|---|---|
| LONGITUDE | Longitude (ecliptic coordinates) |
| LATITUDE | Latitude (ecliptic coordinates) |
| ASCENSION | Right Ascension (equatorial coordinates) |
| DECLINATION | Declination (equatorial coordinates) |
| ALTITUDE | Altitude (horizontal coordinates) |
| AZIMUTH | Azimuth (horizontal coordinates) |
| DISTANCE | Distance in AU |
| MAGNITUDE | Magnitude |
| DIAMETER | Angular diameter |
| HDS | Human Design System positions (gate,line,color,tone,base) |
| STATIONS | Whether or not the object is considered "stationary" |
| LONGITUDE_SPEED | Longitude speed (degrees per day) |
| LATITUDE_SPEED | Latitude speed (degrees per day) |
| ASCENSION_SPEED | Right Ascension speed (degrees per day) |
| DECLINATION_SPEED | Declination speed (degrees per day) |
| DISTANCE_SPEED | Distance speed (AU per day) |
| ALL | All of the above |

### Example

Retrieving `Longitude`, `Latitude` and `Declination` values:

| GET | POST |
|---|---|
|`display=LONGITUDE|LATITUDE|DECLINATION`|`display:["LONGITUDE","LATITUDE","DECLINATION"]`|

<br><br><br>