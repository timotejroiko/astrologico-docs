---
layout: page
title: Endpoints - /v1/dateconversion
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
	.sidebar {
		width: 30%
	}
	.navigation li {
		padding: 5px;
	}
</style>

<br>

## Date Conversion

This endpoint is a standalone version of the date conversion functions included in the main endpoints.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| [Date Parameter](/astrologico/param_date.html) | - | Set date using one of the available date parameters. |
| [Location Parameter](/astrologico/param_location.html) | - | Set location using one of the available location parameters. |
| [options](/astrologico/param_options.html) | array | Set calculation options |

If Date Parameter is an UTC-based parameter, the option `options=utctolocal` is enabled by default.

<br>

### Response

| key | Type | Description |
|---|---|---|
| [STATUS](/astrologico/res_status.html) | string | Contains the response status |
| [date](/astrologico/res_metadata.html) | object | Contains the date object |

<br>

## Sample request

```
GET

https://api.astrologico.org/v1/dateconversion?timestamp=2786472349&location=68|37&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/dateconversion",
header: {
	"Authorization": APIKEY
},
body: {
	timestamp:"2786472349",
	location:[68,37]
}
```

<br>

## Sample response

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
		"siderealTime": "14:49:16"
	}
}
```

<br><br><br>
