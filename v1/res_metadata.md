## Metadata

Metadata contains information about the returned results such as house system used, coordinates used, location, date, etc...

| Value | Type | Descripton |
|---|---|
| [options](#options) | Object | Settings and options information |
| [location](#location) | Object | Geographic coordinates information |
| [date](#date) | Object | Date and time information |
| [referenceDate](#date) | Object | Reference date (returned only when doing operations that require a reference chart) |
| [derivedDate](#date) | Object | Derived date (returned only when using derived chart options) |
| [progressedPlanetsDate](#date) | Object | Progressed date for planets (returned only when using progressed chart options) |
| [progressedHousesDate](#date) | Object | Progressed date for houses (returned only when using progressed chart options) |
| [returnDate](#date) | Object | Return date (returned only when using return chart options) |

<br>

### Metadata - options
{:id="options"}

| Value | Type | Descripton |
|---|---|---|
| zodiacType | String | Zodiac type (tropical/ sidereal) |
| zodiacName | String/Boolean | Ayanamsa name when using sidereal (returns `false` if not using sidereal) |
| positions | String | Planetary positions (apparent / true) |
| coordinates | String | Coordinates system (geocentric / topocentric / heliocentric) |
| astrometric | Boolean | Whether astrometric positions are enabled or not |
| houseSystem | String/Boolean | House system (returns `false` if houses were not enabled) |
| progressed | Boolean | Whether progressed date is being used |
| derived | Boolean | Whether a derived date is being used |
| return | Boolean | Whether a return date is being used |
| planetsDate | String | The date object used for planets |
| housesDate | String | The date object used for houses |
| displayOptions | Array | Array of values that were calculated |

<br>

### Metadata - Location
{:id="location"}

| Value | Type | Descripton |
|---|---|---|
| longitude | Float | Geographic longitude in decimal degrees |
| latitude | Float | Geographic latitude in decimal degrees |
| elevation | Integer | Elevation above sea level in meters |
| queryResult | String | Resulting location (returned only when using `querylocation`) \* |

\* The query result can be localized using the [Language](/astrologico/param_language.html) parameter.

<br>

### Metadata - Date
{:id="date"}

| Value | Type | Descripton |
|---|---|---|
| input | String | Input Date parameter before conversion |
| calendar | String | Calendar used (julian / gregorian) |
| accuracy | Integer | Date accuracy level from 1 to 5 (increases when date is more specific, ie: contains hour, minute, etc...) |
| ISO | String/Array* | Date in ISO format |
| UNIX | Integer/Array* | Date in unix timestamp format |
| [UTCDate](#dateobj) | Object | Object containing individual values in UTC |
| [localDate](#dateobj) | Object | Object containing individual values in local time (returned only when working with non-UTC dates) |
| [timezone](#tz) | Object | Object containing timezone details (returned only when working with non-UTC dates) |
| [JD](#jd) | Object | Object containing date in Julian Days (both variants) |
| siderealTime | String/Array* | Sidereal time at longitude 0 (Greenwich meridian) |
| localSiderealTime | String/Array* | Sidereal time at specified location (returned only when working with non-UTC dates) |
| obliquity | String/Array* | Obliquity of the ecliptic |
| ayanamsa | String/Array* | Value of specified Ayanamsa (returned only when using sidereal) |
| sun | String/Array* | Longitude of the Sun |
| moon | String/Array* | Longitude of the Moon |
| ascendant | String/Array* | Longitude of the Ascendant |

\* Returns an array of values when using the [Ephemeris](/astrologico/v1_ephemeris.html) endpoint.

<br>

### Metadata - Date - UTCDate & LocalDate
{:id="dateobj"}

| Value | Type | Descripton |
|---|---|---|
| day | Integer* | Day (1-31) |
| month | Integer* | Month (1-12) |
| year | Integer* | Full Year |
| hour | Integer* | Hour (0-24) |
| minute | Integer* | Minute (0-60) |
| second | Integer* | Second (0-60) |
| millisecond | Integer* | Millisecond (0-999) |

\* Returns an array of values when using the [Ephemeris](/astrologico/v1_ephemeris.html) endpoint.

<br>

### Metadata - Date - Timezone
{:id="tz"}

| Value | Type | Descripton |
|---|---|---|
| id | String | IANA/tzdb Timezone identifier \*\* |
| name | String | Full Timezone name \* \*\* \*\*\* |
| offsetString | String* | Timezone offset in HH:MM:SS \* |
| offsetMinutes | Integer* | Timezone offset in minutes \* |

\* Returns an array of values when using the [Ephemeris](/astrologico/v1_ephemeris.html) endpoint.

\*\* Returns "custom" when manually specifying an offset in minutes. Returns "not available" if no timezone information exists (dates before circa 1918), in such cases refer to the offset values instead, which will be calculated from geographical longitude (sidereal timezone). For future dates beyond circa 2038, timezones will continue to work but without accounting for summer/winter/daylight-saving time information.

\*\*\* The full Timezone name can be localized using the [Language](/astrologico/param_language.html) parameter.

<br>

### Metadata - Date - Julian Day
{:id="jd"}

| Value | Type | Descripton |
|---|---|---|
| julianDayET | Float* | Julian day in Ephemeris/Terrestrial time |
| julianDayUT | Float* | Julian day in Universal Time |

\* Returns an array of values when using the [Ephemeris](/astrologico/v1_ephemeris.html) endpoint.

<br><br><br>
