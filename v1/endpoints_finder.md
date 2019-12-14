## Finder

This is endpoint is used to lookup the exact moment an object arrives at a specific position in the sky or obtain a specific value for a specific parameter.

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date](parameters_date.md)> | Number/Array | Set date using one of the available date parameters. |
| <[Location](parameters_location.md)> | Number/Array | Set location using one of the available location parameters. |
| [planet](parameters_planets.md) | String | Required. Object ID of the desired object |
| target | Number | Required. Target value to find |
| param | String | Parameter for which to search for the target value (default "LONGITUDE") \* |
| direction | String | Search backwards or forwards in time ("PREV" or "NEXT", default "NEXT") |
| range | Number | Amount of dates to find (default 1, max 20) |
| [options](parameters_options.md) | Array | Set calculation options |
| [timezone](parameters_timezone.md) | String/Integer | Set timezone manually |
| [language](parameters_language.md) | String | Set language to localize certain functions |

\* Available parameters: `"LONGITUDE","LATITUDE","DECLINATION","ASCENSION","ALTITUDE","AZIMUTH","LONGITUDE_SPEED","LATITUDE_SPEED","DECLINATION_SPEED","ASCENSION_SPEED"`

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](response_status.md) | String | Contains the response status |
| [error](response_status.md) | String | Contains the error message in case of error |
| [date](response_metadata.md#date) | Object | Date and time information |
| [result](#result) | Object | result object |
| [keyInfo](response_keyinfo.md) | Object | Contains data about your API key's usage and rate limits |

<br>

### Response - Result

| key | Type | Description |
|---|---|---|
| name | String | Object name |
| param | String | Selected parameter |
| transits | Array | Array of [Transit](#transit) objects |

<br>

### Response - Transit

| key | Type | Description |
|---|---|---|
| value | String | Value of the match found |
| date | Object | [Date](response_metadata.md#date) object for the above match |

<br>

### Sample request

Get the dates for the next 5 times Mercury is at 25 degrees Leo, starting from `October 10, 2015`

```ruby
GET

https://api.astrologico.org/v1/finder?planet=P2&utcdate=10|10|2015&target=145&range=5&key=APIKEY
```

```json
POST

url: "https://api.astrologico.org/v1/finder",
headers: {
	"Authorization": APIKEY
},
body: {
	"utcdate":[10,10,2015],
	"planet":"P2",
	"target":145,
	"range":5
}
```

<br>

### Sample response

```json
{
	"status": "OK",
	"date": {
		"input": "utcdate",
		"calendar": "Gregorian",
		"accuracy": 1,
		"ISO": "2015-10-10T12:00:00.000Z",
		"UNIX": 1444478400000,
		"UTCDate": {
			"day": 10,
			"month": 10,
			"year": 2015,
			"hour": 12,
			"minute": 0,
			"second": 0,
			"milisecond": 0
		},
		"JD": {
			"julianDayET": 2457306.000789167,
			"julianDayUT": 2457306.000002225
		},
		"siderealTime": "13:15:06",
		"obliquity": 23.434798756661944,
		"sun": 196.86409230694173,
		"moon": 169.81132016348744,
		"ascendant": 287.32335872298506
	},
	"result": {
		"name": "Mercury",
		"param": "LONGITUDE",
		"transits": [
			{
				"value": 145.0000021126929,
				"date": {
					"input": "utcdate",
					"calendar": "Gregorian",
					"accuracy": 5,
					"ISO": "2016-07-27T14:58:35.760Z",
					"UNIX": 1469631515760,
					"UTCDate": {
						"day": 27,
						"month": 7,
						"year": 2016,
						"hour": 14,
						"minute": 58,
						"second": 35,
						"milisecond": 760
					},
					"JD": {
						"julianDayET": 2457597.1248141667,
						"julianDayUT": 2457597.1240226314
					},
					"siderealTime": "11:21:28",
					"obliquity": 23.434586317581918,
					"sun": 124.99297854564365,
					"moon": 43.81788828312617,
					"ascendant": 261.14929874480674
				}
			},
			{
				"value": 145.00000209414299,
				"date": {
					"input": "utcdate",
					"calendar": "Gregorian",
					"accuracy": 5,
					"ISO": "2017-07-21T21:19:00.344Z",
					"UNIX": 1500671940344,
					"UTCDate": {
						"day": 21,
						"month": 7,
						"year": 2017,
						"hour": 21,
						"minute": 19,
						"second": 0,
						"milisecond": 344
					},
					"JD": {
						"julianDayET": 2457956.388999167,
						"julianDayUT": 2457956.3882026603
					},
					"siderealTime": "17:18:19",
					"obliquity": 23.434771232284834,
					"sun": 119.28605084029604,
					"moon": 98.18965300507404,
					"ascendant": 348.66566621461845
				}
			},
			{
				"value": 145.0000038018202,
				"date": {
					"input": "utcdate",
					"calendar": "Gregorian",
					"accuracy": 5,
					"ISO": "2018-09-03T04:45:00.584Z",
					"UNIX": 1535949900584,
					"UTCDate": {
						"day": 3,
						"month": 9,
						"year": 2018,
						"hour": 4,
						"minute": 45,
						"second": 0,
						"milisecond": 584
					},
					"JD": {
						"julianDayET": 2458364.698724167,
						"julianDayUT": 2458364.697923833
					},
					"siderealTime": "03:34:06",
					"obliquity": 23.435539722722964,
					"sun": 160.64678285737423,
					"moon": 71.78003199059135,
					"ascendant": 141.14169399550224
				}
			},
			{
				"value": 145.00000168405109,
				"date": {
					"input": "utcdate",
					"calendar": "Gregorian",
					"accuracy": 5,
					"ISO": "2019-08-26T19:14:20.696Z",
					"UNIX": 1566846860696,
					"UTCDate": {
						"day": 26,
						"month": 8,
						"year": 2019,
						"hour": 19,
						"minute": 14,
						"second": 20,
						"milisecond": 696
					},
					"JD": {
						"julianDayET": 2458722.3024291666,
						"julianDayUT": 2458722.301626587
					},
					"siderealTime": "17:33:19",
					"obliquity": 23.436151443194582,
					"sun": 153.2630402613015,
					"moon": 102.8301074859881,
					"ascendant": 352.73708170966347
				}
			},
			{
				"value": 145.00000385984583,
				"date": {
					"input": "utcdate",
					"calendar": "Gregorian",
					"accuracy": 5,
					"ISO": "2020-08-17T13:12:43.495Z",
					"UNIX": 1597669963495,
					"UTCDate": {
						"day": 17,
						"month": 8,
						"year": 2020,
						"hour": 13,
						"minute": 12,
						"second": 43,
						"milisecond": 495
					},
					"JD": {
						"julianDayET": 2459079.051304155,
						"julianDayUT": 2459079.050496555
					},
					"siderealTime": "10:58:12",
					"obliquity": 23.43683412645351,
					"sun": 145.08347288881586,
					"moon": 124.37448636067043,
					"ascendant": 255.7728990320453
				}
			}
		]
	}
}
```

<br>