## Location

This endpoint is a standalone version of the `querylocation` parameter included in the main endpoints.

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| query | String | Required. Name to lookup |
| [language](parameters_language.md) | String | Set language to make a localized search |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](response_status.md) | String | Contains the response status |
| [error](response_status.md) | String | Contains the error message in case of error |
| [location](response_metadata.md#location) | Object | Contains the location object |
| [keyInfo](response_keyinfo.md) | Object | Contains data about your API key's usage and rate limits |

<br>

### Sample request

```
GET

https://api.astrologico.org/v1/location?query=new%20york&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/location",
headers: {
	"Authorization": APIKEY
},
body: {
	query: "new york"
}
```

<br>

### Sample response

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

<br>