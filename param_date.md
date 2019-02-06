---
layout: page
title: Parameters - Date
navigation: 9
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

## Parameters - Date Parameters

There are several Date parameters which are mutually exclusive, you only need to use one of them. If none are used, the request will default to the current date and time.

| Parameter | Type | Input Type | Descripton |
|---|---|---|
| timestamp | Integer | UTC | Unix timestamp in milliseconds |
| jdet | float | UTC | Julian day in ephemeris time or terrestrial time |
| jdut | float | UTC | Julian day in universal time |
| utcdate | array | UTC | Sorted date/time array in UTC |
| localdate | array | LOCAL | Sorted date/time array in local time |

<br>

### Parameters - utcdate/localdate

| Index | Type | Required | Default | Descripton |
|---|---|---|
| 0 | Integer | yes | - | Day |
| 1 | Integer | yes | - | Month |
| 2 | Integer | yes | - | Full year |
| 3 | Integer | no | 12 | Hour |
| 4 | Integer | no | 0 | minute |
| 5 | Float | no | 0 | second |

The `localdate` parameter uses a [Location Parameter](/astrologico/param_location.html) to obtain the correct timezone. Optionally, a custom timezone can be provided using the [Options](/astrologico/param_options.html) parameter. `localdate` turns a `Type1` request into a `Type2` request.

<br><br><br>
