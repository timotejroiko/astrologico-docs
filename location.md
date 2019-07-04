---
layout: page
title: Endpoints - /v1/location
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

## Location

This endpoint is a standalone version of the `querylocation` parameter included in the main endpoints.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| query | string | Name to lookup |
| lang | string | Optional. Get localized result (if available) using a 2-digit language code |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | string | Contains the response status |
| [error](/astrologico/res_status.html) | string | Contains the error message in case of error |
| [location](/astrologico/res_metadata.html#location) | object | Contains the location object |

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
