---
layout: page
title: Endpoints - /v1/ephemerides
navigation: 4
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
	.inner code {
		font-size: 100%;
	}
</style>

<br>

## Ephemerides

The same as the [Chart](/astrologico/chart.html) endpoint but returns arrays of values, instead of single values, corresponding to a time range.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| [Date Parameter](/astrologico/param_date.html) | - | Set date using one of the available date parameters. |
| [Location Parameter](/astrologico/param_location.html) | - | Set location using one of the available location parameters. |
| [range](/astrologico/param_range.html) | array | Set the time range for the ephemerides |
| [options](/astrologico/param_options.html) | array | Set calculation options |
| [display](/astrologico/param_display.html) | array | Set values to return |
| [planets](/astrologico/param_planets.html) | array | Set objects to display |
| [houses](/astrologico/param_houses.html) | string | Set house system to display |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [STATUS](/astrologico/res_status.html) | string | Contains the response status |
| [metadata](/astrologico/res_metadata.html) | object | Contains the configuration used for the calculations |
| [houses](/astrologico/res_houses.html) | object | Contains data for houses, returned only when a house system is selected |
| [planets](/astrologico/res_planets.html) | object | Contains data for planets |

<br>

## Sample request

```
GET

https://api.astrologico.org/v1/chart?utcdate=25|10|2003|12|30|0&location=51.5074|0.1278&planets=P0|P1|P2&range=10|1d&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/chart",
header: {
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

## Sample response

```
{
	"status": "OK",
	"metadata": {
		"options": {
			"zodiacType": "Tropical",
			"zodiacName": "Tropical",
			"ayanamsa": 0,
			"positions": "Apparent",
			"coordinates": "Geocentric",
			"houseSystem": false,
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
			"siderealTime": ["14:43:55","14:47:52","14:51:48","14:55:45","14:59:42","15:03:38","15:07:35","15:11:31","15:15:28","15:19:24"]
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

<br><br><br>
