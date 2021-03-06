## Date Conversion

This endpoint is a standalone version of the date parameters and date conversion functions included in the main endpoints.

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date](parameters_date.md)> | Number/Array | Set date using one of the available date parameters. |
| <[Location](parameters_location.md)> | Number/Array | Find timezone using one of the available location parameters. |
| [options](parameters_options.md) | Array | Set calendar options |
| [timezone](parameters_timezone.md) | String/Integer | Set timezone manually |
| [language](parameters_language.md) | String | Set language to localize certain functions |

If input Date is in UTC and a [Location](parameters_location.md) parameter is provided, the option `UTCTOLOCAL` is enabled by default without aditional cost.

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](response_status.md) | String | Contains the response status |
| [error](response_status.md) | String | Contains the error message in case of error |
| [date](response_metadata.md#date) | Object | Contains the date object |
| [keyInfo](response_keyinfo.md) | Object | Contains data about your API key's usage and rate limits |

<br>

### Sample request

```
GET

https://api.astrologico.org/v1/dateconversion?timestamp=2786472349&location=68|37&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/dateconversion",
headers: {
	"Authorization": APIKEY
},
body: {
	timestamp:"2786472349",
	location:[68,37]
}
```

<br>

### Sample response

```
{
	"status": "OK",
	"date": {
		"input": "timestamp",
		"accuracy": 5,
		"calendar": "Gregorian",
		"ISO": "1970-02-02T06:01:12.349Z",
		"UNIX": 2786472349,
		"UTCDate": {
			"day": 2,
			"month": 2,
			"year": 1970,
			"hour": 6,
			"minute": 1,
			"second": 12,
			"milisecond": 349
		},
		"timezone": {
			"name": "Europe/Moscow",
			"offsetString": "03:00:00",
			"offsetMinutes": 180
		},
		"localDate": {
			"day": 2,
			"month": 2,
			"year": 1970,
			"hour": 9,
			"minute": 1,
			"second": 12,
			"milisecond": 349
		},
		"JD": {
			"julianDayET": 2440619.7513034344,
			"julianDayUT": 2440619.7508373726
		},
		"siderealTime": "14:49:16",
		"localSiderealTime": "19:15:06",
		"obliquity": 23.445560341475534,
		"sun": 312.98161507720755,
		"moon": 256.4926824963518,
		"ascendant": 65.81278581163468
	}
}
```

<br>