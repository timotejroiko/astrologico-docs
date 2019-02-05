---
layout: page
title: Getting Started
navigation: 1
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
</style>

<br>

# Astrologico API

Astrologico API is a fully featured microservice for retrieving astrological calculations and data. All endpoints are `HTTPS` only and available via `GET` and `POST`. Automated key generation is currently not available but you can request a key at our [Discord server (https://discord.gg/jtaCURK)](https://discord.gg/jtaCURK)

The API's base url is `https://api.astrologico.org`.

<br>
  
## GET vs POST

There are two differences between `GET` requests and `POST` requests. In `GET` requests, array parameters should be pipe-delimited query strings, and the API key should be a query-string as well. In `POST` requests, array parameters should be JSON arrays, and the API key should be in the `Authorization` header.

| GET  | POST |
| --- | --- |
| ```?field=value1|value2|value3&key=APIKEY```  | ```header: {Authorization:APIKEY}, body: {field:[value1,value2,value3]}``` |

<br>

## Rate Limits & Request Type

Depending on the endpoint and the parameters used, a request can become a `type1` request or a `type2` request. `type1` requests are simpler and have higher rate limits, while `type2` requests require more resources, and as such have lower rate limits.

When the rate limits are reached, subsequent requests will have a 5 second delay added to them before a response is returned. Our API will continue to be available even if you go over our rate limits, but we advise you to upgrade your key to avoid slowing down your application.

Our current Rate limits are as follows:

| Type1  | Type2 |
| --- | --- |
| 250/day | 50/day |

<br>

## Sample request

```
GET

https://api.astrologico.org/v1/chart?utcdate=25|10|2003|12|30|0&location=51.5074|0.1278&planets=P0|P1|P2&key=APIKEY
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
		"siderealTime": "14:43:55"
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
