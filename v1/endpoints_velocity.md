## Velocity

This is endpoint lets you examine the average speeds and other related data for an object during a given year.

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| [planet](parameters_planets.md) | String | Required. Object ID |
| years | Array | Required. Reference years (max 20) |
| [Options](parameters_options.md) | Array | Set calculation options |
| [Display](parameters_display.md) | Array | Speed values to display (defaults to LONGITUDE_SPEED) |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](response_status.md) | String | Contains the response status |
| [error](response_status.md) | String | Contains the error message in case of error |
| [result](#result) | Object | Object containing the results |
| [keyInfo](response_keyinfo.md) | Object | Contains data about your API key's usage and rate limits |

<br>

### Response - Result

| key | Type | Description |
|---|---|---|
| name | string | Object name |
| <[year](#year)> | Object | Object containing data for a specific year |
| <[year](#year)> | Object | Object containing data for a specific year |
| ... | Object | Object containing data for a specific year |

<br>

### Response - Year

| key | Type | Description |
|---|---|---|
| <[value](#value)> | Object | Object containing data about a specific value |
| <[value](#value)> | Object | Object containing data about a specific value |
| ... | Object | Object containing data about a specific value |

<br>

### Response - Value

Data for the Display value selected in the Year specified.

| key | Type | Description |
|---|---|---|
| averageSpeed | float | Average speed |
| averageAbsoluteSpeed | float | Average absolute speed (negative speed counts as positive) |
| maxSpeed | float | Highest speed recorded |
| minSpeed | float | Lowest speed recorded |
| daysUnderZero | integer | Number of days the speed was negative |
| distanceTraveled | float | Total distance traveled |
| absoluteDistanceTraveled | float | Total absolute distance traveled (negative distance counts as positive) |

<br>

### Sample request

Get Mercury's average Longitude and Latitude speeds for the years 2015 and 2016.

```
GET

https://api.astrologico.org/v1/velocity?planet=P2&years=2015|2016&display=LONGITUDE_SPEED|LATITUDE_SPEED&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/velocity",
headers: {
	"Authorization": APIKEY
},
body: {
	"planet":"P2",
	"years":[2015,2016],
	"display":["LONGITUDE_SPEED","LATITUDE_SPEED"]
}
```

<br>

### Sample response

```
{
    "status": "OK",
    "result": {
        "2015": {
            "longitudeSpeed": {
                "averageSpeed": 1.0017348287489842,
                "averageAbsoluteSpeed": 1.217571964477973,
                "maxSpeed": 2.1365544474489027,
                "minSpeed": -1.2463790115175097,
                "daysUnderZero": 67,
                "distanceTraveled": 365.63321249337923,
                "absoluteDistanceTraveled": 444.41376703446014
            },
            "latitudeSpeed": {
                "averageSpeed": 0.0037461669474823343,
                "averageAbsoluteSpeed": 0.1289808885796248,
                "maxSpeed": 0.3414959127589226,
                "minSpeed": -0.2926520570942449,
                "daysUnderZero": 195,
                "distanceTraveled": 1.367350935831052,
                "absoluteDistanceTraveled": 47.07802433156306
            }
        },
        "2016": {
            "longitudeSpeed": {
                "averageSpeed": 0.9183945427422606,
                "averageAbsoluteSpeed": 1.193767150838056,
                "maxSpeed": 2.17346806799952,
                "minSpeed": -1.3651984231656173,
                "daysUnderZero": 78,
                "distanceTraveled": 335.2140081009251,
                "absoluteDistanceTraveled": 435.72501005589044
            },
            "latitudeSpeed": {
                "averageSpeed": 0.010043435363745107,
                "averageAbsoluteSpeed": 0.1352384054903165,
                "maxSpeed": 0.3322805270427534,
                "minSpeed": -0.2919425858264172,
                "daysUnderZero": 194,
                "distanceTraveled": 3.665853907766964,
                "absoluteDistanceTraveled": 49.36201800396552
            }
        },
        "name": "Mercury"
    }
}
```

<br>