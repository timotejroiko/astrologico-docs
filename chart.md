---
layout: page
title: Endpoints - /v1/chart
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
		padding: 5px;
	}
	@media (min-width: 745px) {
		.sidebar {
			width: 30%;
		}
	}
</style>

<br>

## Chart

This is the primary endpoint through which you can retrieve everything you need to generate accurate astrological charts of various types. All parameters are optional, check each parameter's documentation for default values and additional information.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date Parameter](/astrologico/param_date.html)> | number/array | Set date using one of the available date parameters. |
| <[Location Parameter](/astrologico/param_location.html)> | number/array | Set location using one of the available location parameters. |
| [planets](/astrologico/param_planets.html) | array | Set objects to display |
| [houses](/astrologico/param_houses.html) | string | Set houses to display |
| [display](/astrologico/param_display.html) | array | Set values to display |
| [options](/astrologico/param_options.html) | array | Set calculation options |
| [derived](/astrologico/param_derived.html) | array | Create a derived chart |
| [progression](/astrologico/param_progression.html) | array | Create a progressed chart |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | string | Contains the response status |
| [error](/astrologico/res_status.html) | string | Contains the error message in case of error |
| [metadata](/astrologico/res_metadata.html) | object | Contains information about the data |
| [houses](/astrologico/res_houses.html) | object | Contains data for houses and related points |
| [planets](/astrologico/res_planets.html) | object | Contains data for planets and other objects |

<br>

## Sample request

```
GET

https://api.astrologico.org/v1/chart?utcdate=25|10|2003|12|30&location=51.5074|0.1278&planets=P0|P1|P2&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/chart",
header: {
	"Authorization": APIKEY
},
body: {
	"utcdate":[25,10,2003,12,30],
	"location":[51.5074,0.1278],
	"planets":["P0","P1","P2"]
}
```

<br>

## Sample response

```
"status": "OK",
"metadata": {
	"options": {
		"zodiacType": "Tropical",
		"zodiacName": false,
		"positions": "Apparent",
		"coordinates": "Geocentric",
		"astrometric": false,
		"houseSystem": false,
		"progressed": false,
		"derived": false,
		"planetsDate": "date",
		"housesDate": "date",
		"displayOptions": [
			"LONGITUDE",
			"LONGITUDE_SPEED"
		]
	},
	"location": {
		"latitude": 51.5074,
		"longitude": 0.1278,
		"elevation": 0
	},
	"date": {
		"input": "utcdate",
		"calendar": "Gregorian",
		"accuracy": 3,
		"ISO": "2003-10-25T12:30:00.000Z",
		"UNIX": 1067085000000,
		"UTCDate": {
			"day": 25,
			"month": 10,
			"year": 2003,
			"hour": 12,
			"minute": 30,
			"second": 0,
			"milisecond": 0
		},
		"JD": {
			"julianDayET": 2452938.021576204,
			"julianDayUT": 2452938.0208290154
		},
		"siderealTime": "14:43:55",
		"localSiderealTime": "14:44:26",
		"obliquity": 23.440476763803645,
		"ascendant": 277.785832095783,
		"sun": 211.67580106071702
	}
},
"planets": {
	"P0": {
		"name": "Sun",
		"longitude": 211.67580106071702,
		"longitudeSpeed": 0.9970129304741013
	},
	"P1": {
		"name": "Moon",
		"longitude": 211.47772385703817,
		"longitudeSpeed": 15.041226718480267
	},
	"P2": {
		"name": "Mercury",
		"longitude": 211.74593364533044,
		"longitudeSpeed": 1.660100144491379
	}
}
```

<br><br><br>
