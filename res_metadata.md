---
layout: page
title: Response - Metadata
navigation: 6
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
	.inner code {
		font-size: 100%;
	}
	.navigation li {
		padding: 0.3vh;
	}
	.sidebar {
		min-width: 300px;
	}
	.sidebar .sidebar-main {
	    height: calc(100% - 50px);
	    overflow-y: auto;
	}
	@media (max-width: 745px) {
		.sidebar .sidebar-main {
		    height: calc(100% - 320px);
		}
	}
</style>

<script>
	window.onload = function(){
		if (location.hash) {
			let target = location.hash;
			document.querySelector(".content").scroll({top:document.querySelector(target).offsetTop,behavior:"smooth"})
		}
	}
</script>

<br>

## Metadata

Metadata contains information about the returned results such as house system, coordinates used, location, date, etc...

| Value | Type | Descripton |
|---|---|
| [options](#options) | object | Settings and options information |
| [location](#location) | object | Geographic coordinates information |
| [date](#date) | object | Date and time information |
| [referenceDate](#date) | object | Reference date (returned only when doing operations that require a reference chart) |
| [derivedDate](#date) | object | Derived date (returned only when using derived chart options) |
| [progressedPlanetsDate](#date) | object | Progressed date for planets (returned only when using progressed chart options) |
| [progressedHousesDate](#date) | object | Progressed date for houses (returned only when using progressed chart options) |
| [returnDate](#date) | object | Return date (returned only when using return chart options) |

<br>

### Metadata - options
{:id="options"}

| Value | Type | Descripton |
|---|---|---|
| zodiacType | string | Zodiac type (tropical or sidereal) |
| zodiacName | string | Zodiac name when using sidereal (returns `false` if tropical) |
| positions | string | Planetary positions (apparent / true) |
| coordinates | string | Coordinates system (geocentric / topocentric / heliocentric) |
| astrometric | boolean | Whether astrometric positions are enabled or not |
| houseSystem | string/boolean | House system (returns `false` if houses were not enabled) |
| progressed | boolean | Whether progressed date is being used or not |
| derived | boolean | Whether a derived date is being used or not |
| return | boolean | Whether a return date is being used or not |
| planetsDate | string | The date object used for planets |
| housesDate | string | The date object used for houses |
| displayOptions | array | Array of values to be calculated |

<br>

### Metadata - Location
{:id="location"}

| Value | Type | Descripton |
|---|---|---|
| latitude | float | Geographic latitude in decimal degrees |
| longitude | float | Geographic longitude in decimal degrees |
| elevation | float | Elevation above sea level in meters |
| queryResult | string | Resulting location (returned only when using `querylocation`) |

<br>

### Metadata - Date
{:id="date"}

| Value | Type | Descripton |
|---|---|---|
| input | string | Selected date parameter |
| calendar | string | Calendar used (julian / gregorian) |
| accuracy | integer | Date accuracy level from 1 to 5 (increases when date is more specific, ie: contains hour, minute, etc...) |
| ISO | string/array* | Date in ISO format |
| UNIX | integer/array* | Date in unix timestamp format |
| [UTCDate](#dateobj) | object | Object containing individual date values in UTC |
| [localDate](#dateobj) | object | Object containing individual date values in local time (returned only when using non-UTC dates) |
| [timezone](#tz) | object | Object containing timezone details (returned only when using non-UTC dates) |
| [JD](#jd) | object | Object containing date in Julian Days (both variants) |
| siderealTime | string/array* | Sidereal time at longitude 0 (Greenwich meridian) |
| localSiderealTime | string/array* | Sidereal time at specified location (returned only when using non-UTC dates) |
| obliquity | string/array* | Obliquity of the ecliptic |
| ayanamsa | string/array* | Value of specified Ayanamsa (returned only when using sidereal) |
| sun | string/array* | Longitude of the Sun |
| moon | string/array* | Longitude of the Moon |
| ascendant | string/array* | Longitude of the Ascendant |

\* Returns array of values when using the `ephemeris` endpoint.

<br>

### Metadata - Date - Date object
{:id="dateobj"}

| Value | Type | Descripton |
|---|---|---|
| day | integer | Day number (1-31) |
| month | integer | Month number (1-12) |
| year | integer | Full year number |
| hour | integer | Hour (0-24) |
| minute | integer | Minute (1-60) |
| second | integer | Second (0-60) |
| millisecond | integer | Millisecond (0-999) |

<br>

### Metadata - Date - Timezone
{:id="tz"}

| Value | Type | Descripton |
|---|---|---|
| name | string | Timezone identifier according to the tz-database \* |
| abbr | string | Timezone abbreviation \* |
| offsetString | string | Timezone offset in HH:MM:SS |
| offsetMinutes | integer | Timezone offset in minutes |

\* Returns "custom" when manually specifying an offset in minutes. Returns "not available" if timezone information doesnt exist, in such cases refer to the offset values.

<br>

### Metadata - Date - Julian Day
{:id="jd"}

| Value | Type | Descripton |
|---|---|---|
| julianDayET | float | Julian day in Ephemeris/Terrestrial time |
| julianDayUT | float | Julian day in Universal Time |

<br><br><br>
