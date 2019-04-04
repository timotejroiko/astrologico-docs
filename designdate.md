---
layout: page
title: Endpoints - /v1/designdate
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

<script>
	window.onload = function(){
		if (location.hash) {
			let target = location.hash;
			document.querySelector(".content").scroll({top:document.querySelector(target).offsetTop,behavior:"smooth"})
		}
	}
</script>

<br>

## Design Date

This endpoint is used to find the "design date" of a human design chart and other derived dates. The design date can then used together with the birth date to obtain the two charts that make up the human design system.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| [Date Parameter](/astrologico/param_date.html) | - | Set date using one of the available date parameters. |
| [Location Parameter](/astrologico/param_location.html) | - | Find timezone using one of the available location parameters. |
| [options](/astrologico/param_options.html) | array | Set timezone using manual options |
| [mode](#mode) | integer | Optional. Set the design date type |

<br>

### Parameters - Mode
{:id="mode"}

| Mode | Descripton |
|---|---|
| 0 | Default. prenatal solar design. |
| 1 | prenatal lunar design. |
| 2 | prenatal solar minute design. |
| 3 | prenatal lunar minute design. |
| 4 | postnatal solar design. |
| 5 | postnatal lunar design. |
| 6 | postnatal solar minute design. |
| 7 | postnatal lunar minute design. |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | string | Contains the response status |
| [date](/astrologico/res_metadata.html#date) | object | Contains the date object |

<br>

## Sample request

```
GET

https://api.astrologico.org/v1/designdate?utcdate=10|3|1991|12&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/designdate",
header: {
	"Authorization": APIKEY
},
body: {
	utcdate: [10,3,1991,12]
}
```

<br>

## Sample response

```
{
	"status": "OK",
	"date": {
		"input": "utcdate",
		"calendar": "Gregorian",
		"accuracy": 2,
		"ISO": "1990-12-13T16:36:34.809Z",
		"UNIX": 661106194809,
		"UTCDate": {
			"day": 13,
			"month": 12,
			"year": 1990,
			"hour": 16,
			"minute": 36,
			"second": 34,
			"milisecond": 809
		},
		"JD": {
			"julianDayET": 2448239.1927314005,
			"julianDayUT": 2448239.1920655635
		},
		"siderealTime": "22:04:59",
		"localSiderealTime": "22:04:59"
	}
}
```

<br><br><br>
