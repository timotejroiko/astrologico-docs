## Scanner

This endpoint attempts to find all objects of a given type located in a certain position. Requests to this endpoint are pretty expensive and might often be throttled to prevent abuse, so expect them to be slow (5-10 seconds per request on average).

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date](parameters_date.md)> | Number/Array | Set date using one of the available date parameters. |
| <[Location](parameters_location.md)> | Number/Array | Set location using one of the available location parameters. |
| [type](#type) | String | Object type to scan |
| [param](#param) | String | Parameter to scan for matching target value |
| [target](#target) | Number | Target value |
| [options](parameters_options.md) | Array | Set calculation options |
| [sidereal](parameters_sidereal.md) | Integer/Array | Enable the Sidereal zodiac and set an Ayanamsa |
| [timezone](parameters_timezone.md) | String/Integer | Set timezone manually |

<br>

### Parameters - Type

| Type | Descripton |
|---|---|
| A | Asteroids |
| S | Stars |
| O | Planets, Hypotheticals, Comets, Arabic parts and other objects |
| D | Deep scan of stars and celestial objects from the simbad database \* |

\* In deep scan mode, a secondary target value is required.

<br>

### Parameters - Param

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
| [status](response_status.md) | String | Contains the response status |
| [error](response_status.md) | String | Contains the error message in case of error |
| [results](#results) | Array | An array of all objects found nearby the given coordinates |
| [keyInfo](response_keyinfo.md) | Object | Contains data about your API key's usage and rate limits |

<br>

### Response - Results

The results field is an array of objects which contain the following fields.

| key | Type | Description |
|---|---|---|
| name | String | Object name |
| names | Array | Array of names for objects with multiple names (returned instead of `name` for stars and arabic parts) |
| designations | Array | Array of official designations (returned for stars only) |
| &lt;param&gt; | Number | The position of the object in the supplied parameter |
| id | String | Object ID to use with other endpoints (not available in deep scan mode) |

<br>

### Sample request

```
GET

https://api.astrologico.org/v1/scanner?utcdate=10|10|2015&target=2&type=O&param=LONGITUDE&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/scanner",
headers: {
	"Authorization": APIKEY
},
body: {
	utcdate: [10,10,2015],
	target: 2,
	type: "O",
	param: "LONGITUDE"
}
```

<br>

### Sample response

```
{
	"status": "OK",
	"result": [
		{
			"name": "57P/duToit-Neujmin-Delporte",
			"longitude": 1.8999676817825324,
			"id": "C61"
		},
		{
			"name": "231P/LINEAR-NEAT",
			"longitude": 2.369568993038678,
			"id": "C307"
		},
		{
			"name": "C/1874 Q1 (Coggia)",
			"longitude": 0.816902382232026,
			"id": "C505"
		},
		{
			"name": "C/2006 V1 (Catalina)",
			"longitude": 2.3589702048429606,
			"id": "C845"
		},
		{
			"name": "P/2005 E1 (Tubbiolo)",
			"longitude": 1.5435894405720267,
			"id": "C1196"
		},
		{
			"name": "P/2010 H4 (Scotti)",
			"longitude": 0.5188327578728367,
			"id": "C1252"
		},
		{
			"name": "True South Node",
			"longitude": 1.0430285550213796,
				"id": "P24"
		}
	]
}
```

<br>