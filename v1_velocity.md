---
layout: page
title: Endpoints - /v1/velocity
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

## Velocity

This is endpoint lets you examine the average speeds and other related data for an object during a given year.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| [planet](/astrologico/param_planets.html) | string | Object ID |
| years | array | Reference years (max 20) |
| [Options](/astrologico/param_options.html) | array | Optional. Set calculation options |
| [Display](/astrologico/param_display.html) | array | Optional. Speed values to display (defaults to LONGITUDE_SPEED) |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | string | Contains the response status |
| [error](/astrologico/res_status.html) | string | Contains the error message in case of error |
| [result](#result) | object | Object containing the results |

<br>

### Response - Result
{:id="result"}

| key | Type | Description |
|---|---|---|
| name | string | Object name |
| <[year](#year)> | object | Object containing data for a specific year |

<br>

### Response - <Year>
{:id="year"}

| key | Type | Description |
|---|---|---|
| <[value](#value)> | object | Object containing data about a specific value |

<br>

### Response - <Value>
{:id="value"}

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

## Sample request

Get the dates for the next 10 solar returns for a person born in timestamp `739847298374`, starting from `October 10, 2015`

```
GET

https://api.astrologico.org/v1/velocity?planet=P2&years=2015|2016&display=LONGITUDE_SPEED|LATITUDE_SPEED&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/velocity",
header: {
	"Authorization": APIKEY
},
body: {
	"planet":"P2",
	"years":[2015,2016],
	"display":["LONGITUDE_SPEED","LATITUDE_SPEED"]
}
```

<br>

## Sample response

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

<br><br><br>
