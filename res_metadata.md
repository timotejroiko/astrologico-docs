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
		padding: 5px;
	}
	@media (min-width: 745px) {
		.sidebar {
			width: 30%;
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

## Response - Metadata

Metadata contains information about the returned results such as house system, coordinates used, location, date, etc...

| Value | Type | Descripton |
|---|---|
| [options](#options) | object | Settings and options information |
| [location](#location) | object | Geographic coordinates information |
| [date](#date) | object | Date and time information |

<br>

### Parameters - options
{:id="options"}

| Value | Type | Descripton |
|---|---|---|
| zodiacType | string | Zodiac type (tropical or sidereal) |
| zodiacName | string | Zodiac name (tropical or name of the selected ayanamsa) |
| ayanamsa | float/array* | Value of the selected ayanamsa in decimal degrees |
| positions | string | Planetary positions (apparent / true / astrometric) |
| coordinates | string | Coordinates system (geocentric / topocentric / heliocentric) |
| houseSystem | string | House system (returns `false` if houses were not enabled) |
| displayOptions | array | Array of values to be calculated |
| obliquity | float/array* | Obliquity of the ecliptic in decimal degrees |

\* Returns array of values corresponding to the array of dates when using the `ephemerides` endpoint.

<br>

### Parameters - Location
{:id="location"}

| Value | Type | Descripton |
|---|---|---|
| latitude | float | Geographic latitude in decimal degrees |
| longitude | float | Geographic longitude in decimal degrees |
| elevation | float | Elevation above sea level in meters |
| queryResult | string | Resulting location (returned only when using `querylocation`) |

<br>

### Parameters - Date
{:id="date"}

| Value | Type | Descripton |
|---|---|---|
| input | string | Selected date parameter |
| calendar | string | Calendar used (julian / gregorian) |
| accuracy | integer | Date accuracy level from 1 to 5 (increases when date is more specific, ie: contains hour, minute, etc...) |
| ISO | string/array* | Date in ISO format |
| UNIX | integer/array* | Date in unix timestamp format |
| [UTCDate](#dateobj) | object | Object containing individual date values in UTC |
| [localDate](#dateobj) | object | Object containing individual date values in local time (returned only when doing non-UTC operations) |
| [timezone](#tz) | object | Object containing timezone details (returned only when doing non-UTC operations) |
| [JD](#jd) | object | Object containing date in Julian Days (both variants) |
| siderealTime | string/array* | Sidereal time at longitude 0 (Greenwich meridian) |
| localSiderealTime | string/array* | Sidereal time at the selected coordinates |

\* Returns array of values corresponding to the array of dates when using the `ephemerides` endpoint.

<br>

### Parameters - Date - UTCDate/localDate
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

### Parameters - Date - Timezone
{:id="tz"}

| Value | Type | Descripton |
|---|---|---|
| name | string | Timezone identifier according to the IANA TZ Database |
| offsetString | string | Timezone offset in HH:MM:SS |
| offsetMinutes | integer | Timezone offset in minutes |

<br>

### Parameters - Date - Julian Day
{:id="jd"}

| Value | Type | Descripton |
|---|---|---|
| julianDayET | float | Julian day in Ephemeris/Terrestrial time |
| julianDayUT | float | Julian day in Universal Time |

<br><br><br>
