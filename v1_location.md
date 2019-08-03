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
		padding: 0.3vh;
	}
	.sidebar {
		min-width: 300px;
	}
	.sidebar .sidebar-main {
	    height: calc(100% - 50px);
	    overflow-y: auto;
	}
	@media (max-width: 745px) {
		.sidebar .sidebar-main {
		    height: calc(100% - 320px);
		}
	}
</style>

<br>

## Location

This endpoint is a standalone version of the `querylocation` parameter included in the main endpoints.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| query | String | Required. Name to lookup |
| [language](/astrologico/param_language.html) | String | Set language to make a localized search |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | String | Contains the response status |
| [error](/astrologico/res_status.html) | String | Contains the error message in case of error |
| [location](/astrologico/res_metadata.html#location) | Object | Contains the location object |
| [keyInfo](/astrologico/res_keyinfo.html) | Object | Contains data about your API key's usage and rate limits |

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
