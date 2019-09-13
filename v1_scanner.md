---
layout: page
title: Endpoints - /v1/scanner
navigation: 3
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

<br>

## Scanner

This endpoint attempts to find all objects of a given type located in a certain position. Requests to this endpoint are pretty expensive and might often be throttled to prevent abuse and resource starvation, so expect them to be slow (5-10 seconds per request on average).

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date](/astrologico/param_date.html)> | Number/Array | Set date using one of the available date parameters. |
| <[Location](/astrologico/param_location.html)> | Number/Array | Set location using one of the available location parameters. |
| [type](#type) | String | Object type to scan |
| [param](#param) | String | Parameter to scan for matching target value |
| [target](#target) | Number | Target value |
| [options](/astrologico/param_options.html) | Array | Set calculation options |
| [sidereal](/astrologico/param_sidereal.html) | Integer/Array | Enable the Sidereal zodiac and set an Ayanamsa |
| [timezone](/astrologico/param_timezone.html) | String/Integer | Set timezone manually |

<br>

### Parameters - Type
{:id="type"}

| Type | Descripton |
|---|---|
| A | Asteroids |
| S | Stars |
| O | Planets, Hypotheticals, Comets, Arabic parts and other objects |
| D | Deep scan of stars and celestial objects from the simbad database \* |

\* In deep scan mode, a secondary target value is required.

<br>

### Parameters - Param
{:id="param"}

| Accepted Parameters |
|---|
| LONGITUDE |
| LATITUDE |
| ASCENSION |
| DECLINATION |
| AZIMUTH |
| ALTITUDE |

<br>

### Parameters - Target
{:id="target"}

| Accepted Values | Types |
|---|---|
| number from 0 to 360 | LONGITUDE, ASCENSION, AZIMUTH |
| number from -90 to 90 | LATITUDE, DECLINATION, ALTITUDE |
| number,number | Deep scan mode \* |

\* In deep scan mode, the `target` parameter should contain a pair of two comma-separated values (lat-lon, asc-dec, azi-alt). For example, if the selected `param` is `LONGITUDE`, the `target` field should contain values for `LONGITUDE` and `LATITUDE`, or if the selected `param` is `DECLINATION`, then it should contain values for `DECLINATION` and `ASCENSION`, and so on... The first value always corresponds to the selected `param` and the second value corresponds to its maching coordinate pair.

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | String | Contains the response status |
| [error](/astrologico/res_status.html) | String | Contains the error message in case of error |
| [results](#results) | Array | An array of all objects found nearby the given coordinates |
| [keyInfo](/astrologico/res_keyinfo.html) | Object | Contains data about your API key's usage and rate limits |

<br>

### Response - Results
{:id="results"}

The results field is an array of objects which contain the following fields.

| key | Type | Description |
|---|---|---|
| name | String | Object name |
| names | Array | Array of names for objects with multiple names (returned instead of `name` for stars and arabic parts) |
| designations | Array | Array of official designations (returned for stars only) |
| <param> | Number | The position of the object in the supplied parameter |
| id | String | Object ID to use with other endpoints (not available in deep scan mode) |

<br>

## Sample request

```
GET

https://api.astrologico.org/v1/location?query=new%20york&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/location",
header: {
	"Authorization": APIKEY
},
body: {
	query: "new york"
}
```

<br>

## Sample response

```
{
	"status": "OK",
	"location": {
		"queryResult": "New York, New York, United States",
		"longitude": -73.9808,
		"latitude": 40.7648,
		"elevation": 30
	}
}
```

<br><br><br>
