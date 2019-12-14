## Ephemeris

The same as the [Chart](endpoints_chart.md) endpoint but returns arrays of values corresponding to a time range.

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date](/astrologico/param_date.md)> | Number/Array | Set date using one of the available date parameters. |
| <[Location](/astrologico/param_location.md)> | Number/Array | Set location using one of the available location parameters. |
| [range](#range) | Array | Required. Set the time range |
| [planets](/astrologico/param_planets.md) | Array | Set objects to display |
| [houses](/astrologico/param_houses.md) | Array | Set houses to display |
| [options](/astrologico/param_options.md) | Array | Set calculation options |
| [sidereal](/astrologico/param_sidereal.md) | Integer/Array | Enable the Sidereal zodiac and set an Ayanamsa |
| [display](/astrologico/param_display.md) | Array | Set values to display |
| [stations](/astrologico/param_display.md) | Array | Customize the "stationary" display option |
| [derived](/astrologico/param_derived.md) | Array | Ephemeris for a derived chart |
| [progression](/astrologico/param_progression.md) | array | Ephemeris for a progressed chart |
| [timezone](/astrologico/param_timezone.md) | String/Integer | Set timezone manually |
| [language](/astrologico/param_language.md) | String | Set language to localize certain functions |

<br>

### Parameters - Range

The range parameter is an indexed array containing the amount of dates to calculate and the interval between each date.

| Index | Type | Description |
|---|---|---|
| 0 | Integer | Amount of dates (max 1000) |
| 1 | String | Interval between each date. See examples |

Here are a few examples:

| GET | POST | Description |
|---|---|---|
| &range=10\|1d | range:[10,\"1d\"] | Return 10 dates in 1 day intervals |
| &range=50\|5h | range:[50,\"5h\"] | Return 50 dates in 5 hour intervals |
| &range=5\|1y | range:[5,\"1y\"] | Return 5 dates in 1 year intervals |
| &range=100\|30m | range:[100,\"30m\"] | Return 100 dates in 30 minute intervals |
| &range=12\|1M | range:[12,\"1M\"] | Return 12 dates in 1 month intervals |
| &range=10\|1d | range:[10,\"-1d\"] | Return 10 dates in 1 day intervals backwards in time |

Interval supports years `y`, months `M`, weeks `w`, days `d`, hours `h`, minutes `m`, seconds `s` and milliseconds `ms`

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

```
GET

https://api.astrologico.org/v1/ephemeris?utcdate=25|10|2003|12|30|0&location=51.5074|0.1278&planets=P0|P1|P2&range=10|1d&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/ephemeris",
headers: {
	"Authorization": APIKEY
},
body: {
	"utcdate":[25,10,2003,12,30,0],
	"location":[51.5074,0.1278],
	"planets":["P0","P1","P2"],
	"range":[10,"1d"]
}
```

<br>

### Sample response

```
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
			"accuracy": 4,
			"ISO": ["2003-10-25T12:30:00.000Z","2003-10-26T12:30:00.000Z","2003-10-27T12:30:00.000Z","2003-10-28T12:30:00.000Z","2003-10-29T12:30:00.000Z","2003-10-30T12:30:00.000Z","2003-10-31T12:30:00.000Z","2003-11-01T12:30:00.000Z","2003-11-02T12:30:00.000Z","2003-11-03T12:30:00.000Z"],
			"UNIX": [1067085000000,1067171400000,1067257800000,1067344200000,1067430600000,1067517000000,1067603400000,1067689800000,1067776200000,1067862600000],
			"UTCDate": {
				"day": [25,26,27,28,29,30,31,1,2,3],
				"month": [10,10,10,10,10,10,10,11,11,11],
				"year": [2003,2003,2003,2003,2003,2003,2003,2003,2003,2003],
				"hour": [12,12,12,12,12,12,12,12,12,12],
				"minute": [30,30,30,30,30,30,30,30,30,30],
				"second": [0,0,0,0,0,0,0,0,0,0],
				"milisecond": [0,0,0,0,0,0,0,0,0,0]
			},
			"JD": {
				"julianDayET": [2452938.021576204,2452939.021576204,2452940.021576204,2452941.021576204,2452942.021576204,2452943.021576204,2452944.021576204,2452945.021576204,2452946.021576204,2452947.021576204],
				"julianDayUT": [2452938.0208290154,2452939.020829012,2452940.0208290094,2452941.0208290066,2452942.020829004,2452943.020829001,2452944.020828998,2452945.0208289954,2452946.0208289926,2452947.02082899]
			},
			"siderealTime": ["14:43:55","14:47:52","14:51:48","14:55:45","14:59:42","15:03:38","15:07:35","15:11:31","15:15:28","15:19:24"],
			"obliquity": [23.440476763803645,23.44045713805244,23.440436567877978,23.440419941964763,23.440410665623396,23.44040965574477,23.440415460603322,23.44042518643726,23.440435584277044,23.440443819641295],
			"sun": [211.67580106071702,212.67309288480732,213.6709264383752,214.6692739871689,215.668105926189,216.66739545106427,217.66712256134699,218.66727592543532,219.66785247437463,220.66885567306372],
			"moon": [211.47772385703783,226.55818307300166,241.61644875672698,256.5130728317905,271.13767388720777,285.41835762679926,299.3221257347152,312.8487438679878,326.02153348514264,338.8779927610498],
			"ascendant": [277.785832095783,278.79625355976304,279.8215768997102,280.8624265747237,281.91945027117686,282.993324563501,284.0847591177119,285.1944980184321,286.3233187600409,287.47203033888024]
			
		}
	},
	"planets": {
		"P0": {
			"name": "Sun",
			"longitude": [211.67580106071702,212.67309288480732,213.67092643837518,214.66927398716888,215.668105926189,216.66739545106427,217.66712256134699,218.6672759254353,219.6678524743746,220.66885567306372],
			"longitudeSpeed": [0.9970129304741013,0.9975667946937826,0.9980951796137378,0.9985941892089789,0.9990642371774938,0.9995104000301557,0.9999408272810469,1.0003643019658839,1.0007883340748247,1.0012184464482936]
		},
		"P1": {
			"name": "Moon",
			"longitude": [211.47772385703817,226.55818307300203,241.61644875672727,256.5130728317908,271.13767388720794,285.4183576267993,299.3221257347153,312.8487438679878,326.0215334851425,338.87799276104965],
			"longitudeSpeed": [15.041226718480267,15.094240371267448,14.998711888022102,14.775917642635632,14.461225537945944,14.094688129867192,13.71293257988289,13.34434904318636,13.007641695275144,12.71273648930341]
		},
		"P2": {
			"name": "Mercury",
			"longitude": [211.74593364533044,213.40136037868882,215.04758324969845,216.68481094116143,218.31323772200017,219.93308191177485,221.5445851911179,223.14800849579473,224.7436266943979,226.33172266950675],
			"longitudeSpeed": [1.660100144491379,1.65078655020489,1.6416977420072187,1.6327961560225,1.624100221468861,1.615634831143394,1.6074215165542753,1.5994770800385383,1.591812505292202,1.584432882862892]
		}
	}
}
```

<br>