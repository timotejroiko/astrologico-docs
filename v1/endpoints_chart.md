## Chart

This is the primary endpoint through which you can retrieve everything you need to generate accurate astrological charts of various types. All parameters are optional but be check each parameter's documentation page for default values and additional information.

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date](parameters_date.md)> | Number/Array | Set date using one of the available date parameters. |
| <[Location](parameters_location.md)> | Number/Array | Set location using one of the available location parameters. |
| [planets](parameters_planets.md) | Array | Set planets and objects to display |
| [houses](parameters_houses.md) | Array | Set houses to display |
| [options](parameters_options.md) | Array | Set calculation options |
| [sidereal](parameters_sidereal.md) | Integer/Array | Enable the Sidereal zodiac and set an Ayanamsa |
| [display](parameters_display.md) | Array | Set values to display |
| [stations](parameters_display.md) | Array | Customize the "stationary" display option |
| [derived](parameters_derived.md) | Array | Create a derived chart |
| [progression](parameters_progression.md) | Array | Create a progressed chart |
| [return](parameters_return.md) | Array | Create a return chart |
| [timezone](parameters_timezone.md) | String/Integer | Set timezone manually |
| [language](parameters_language.md) | String | Set language to localize certain functions |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](response_status.md) | String | Contains the response status |
| [error](response_status.md) | String | Contains the error message in case of error |
| [metadata](response_metadata.md) | Object | Contains information about the data |
| [houses](response_houses.md) | Object | Contains data for houses and related points |
| [planets](response_planets.md) | Object | Contains data for planets and other objects |
| [keyInfo](response_keyinfo.md) | Object | Contains data about your API key's usage and rate limits |

<br>

### Sample request

```ruby
GET

https://api.astrologico.org/v1/chart?utcdate=25|10|2003|12|30&location=51.5074|0.1278&planets=P0|P1|P2&key=APIKEY
```

```json
POST

url: "https://api.astrologico.org/v1/chart",
headers: {
	"Authorization": APIKEY
},
body: {
	"utcdate":[25,10,2003,12,30],
	"location":[51.5074,0.1278],
	"planets":["P0","P1","P2"]
}
```

<br>

### Sample response

```json
{
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
			"return": false,
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
			"obliquity": 23.440476763803645,
			"sun": 211.67580106071668,
			"moon": 211.47772385703783,
			"ascendant": 277.785832095783
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
}
```

<br>