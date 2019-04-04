---
layout: page
title: Parameters - Options
navigation: 5
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

## Parameters - Options

An array of options to configure several chart generation settings, timezones, etc...

| option | Descripton |
|---|---|
| TRUEPOSITIONS | Return True positions instead of Apparent |
| HELIOCENTRIC | Return Heliocentric positions instead of Geocentric |
| TOPOCENTRIC | Return Topocentric positions instead of Geocentric |
| ASTROMETRIC | Return Astrometric positions (disable Aberration of Light and Gravitational Deflection) |
| [SIDEREAL:N](#sidereal) | Return Sidereal positions instead of Tropical by specifying an Ayanamsa |
| [STATIONS:N](#stations) | Number of days an object should be considered "stationary" when stations are enabled |
| JULIAN | Use Julian calendar instead of automatic |
| GREGORIAN | Use Gregorian calendar instead of automatic |
| UTCTOLOCAL | Return Local Date when input is a UTC date (becomes a `Type2` request) |
| [TZ:N](#timezone) | Set a custom timezone |

<br>

### Parameters - Options - Sidereal
{:id="sidereal"}

The Sidereal option can be used to create sidreal and vedic charts. It offers several built in Ayanamsas, as well as an option to set a custom Ayanamsa. If no Ayanamsa is specified, it defaults to 0 (Fagan/Bradley).

| N | Type | Ayanamsa |
|---|---|---|
| 0 | Integer | Fagan/Bradley |
| 1 | Integer | Lahiri |
| 2 | Integer | De Luce |
| 3 | Integer | Raman |
| 4 | Integer | Usha/Shashi |
| 5 | Integer | Krishnamurti |
| 6 | Integer | Djwhal Khul |
| 7 | Integer | Yukteshwar |
| 8 | Integer | J.N. Bhasin |
| 9 | Integer | Babylonian/Kugler 1 |
| 10 | Integer | Babylonian/Kugler 2 |
| 11 | Integer | Babylonian/Kugler 3 |
| 12 | Integer | Babylonian/Huber |
| 13 | Integer | Babylonian/Eta Piscium |
| 14 | Integer | Babylonian/Aldebaran = 15 Taurus |
| 15 | Integer | Hipparchos |
| 16 | Integer | Sassanian |
| 17 | Integer | Galactic Center = 0 Sagittarius |
| 18 | Integer | J2000 |
| 19 | Integer | J1900 |
| 20 | Integer | B1950 |
| 21 | Integer | Suryasiddhanta |
| 22 | Integer | Suryasiddhanta (mean Sun) |
| 23 | Integer | Aryabhata |
| 24 | Integer | Aryabhata (mean Sun) |
| 25 | Integer | SS Revati |
| 26 | Integer | SS Citra |
| 27 | Integer | True Citra |
| 28 | Integer | True Revati |
| 29 | Integer | True Pushya (PVR Narasimha Rao) |
| 30 | Integer | Galactic Center (Gil Brand) |
| 31 | Integer | Galactic Equator (IAU1958) |
| 32 | Integer | Galactic Equator |
| 33 | Integer | Galactic Equator mid-Mula |
| 34 | Integer | Skydram (Mardyks) |
| 35 | Integer | True Mula (Chandra Hari) |
| 36 | Integer | Dhruva / Galactic Center / Mula (Wilhelm) |
| 37 | Integer | Aryabhata 522 |
| 38 | Integer | Babylonian/Britton |
| reference,initial | String | Custom Ayanamsa |

A custom ayanamsa can be set by specifying a reference date and an initial value. Reference date should be in Julian Days ET/TT (Ephemeris/Terrestrial Time) and the initial value should be the Ayanamsa value in decimal (number of degrees difference from Tropical)

|GET Example|POST Example|Description|
|---|---|---|
|`options=SIDEREAL:5`|`options:["SIDEREAL:5"]`|Set Ayanamsa to Krishnamurti|
|`options=SIDEREAL:2451545,25`|`options:["SIDEREAL:2451545,25"]`|Set Ayanamsa to 25 degrees at J2000 (noon of January 1st, 2000)|

<br>

### Parameters - Options - Stations
{:id="stations"}

When [Display](/astrologico/param_display.html) includes Stations, `true` is returned if the object is within 1 day of its zero point (when it switches directions). This option can be used to change the amount of days an object should be considered "Stationary".

|GET Example|POST Example|Description|
|---|---|---|
|`options=STATIONS:2`|`options:["STATIONS:2"]`|Consider an object "stationary" if within 2 days of its zero point|

<br>

### Parameters - Options - TZ
{:id="timezone"}

Allows you to specify a manual timezone when calculating between Local and UTC dates. Timezone can be set as an offset in minutes or as a timezone string according to the [TZdata specification](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

|GET Example|POST Example|Description|
|---|---|---|
|`options=TZ:America/New_York`|`options:["TZ:America/New_York"]`|Set timezone to America/New_York|
|`options=TZ:+300`|`options:["TZ:+300"]`|Set timezone to 300 minutes ahead of UTC|

<br><br><br>
