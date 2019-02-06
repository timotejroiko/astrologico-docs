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
|---|---|---|---|
| timestamp | Integer | UTC | Unix timestamp in milliseconds |
| jdet | float | UTC | Julian day in ephemeris time or terrestrial time |
| jdut | float | UTC | Julian day in universal time |
| utcdate | array | UTC | Sorted date/time array in UTC |
| [localdate](#datearray){:target="_blank"} | array | LOCAL | Sorted date/time array in local time |

<br>

### Parameters - utcdate/localdate
{:hreflang="de"}

| Index | Type | Required | Default | Descripton |
|---|---|---|---|---|
| 0 | Integer | yes | - | Day |
| 1 | Integer | yes | - | Month |
| 2 | Integer | yes | - | Full year |
| 3 | Integer | no | 12 | Hour (in 24h format) |
| 4 | Integer | no | 0 | minute |
| 5 | Float | no | 0 | second (milliseconds in decimal) |

The `localdate` parameter uses a [Location Parameter](/astrologico/param_location.html) to obtain the correct timezone. Optionally, a custom timezone can be provided using the [Options](/astrologico/param_options.html) parameter. `localdate` turns a `Type1` request into a `Type2` request.

<br>

### Parameters - Date Parameters Examples

Here's an example of how each parameter should be used to generate a chart for `February 15, 1995 - 1:53pm, in New York USA`

| Parameter | GET Request | POST Request
|---|---|---|
| timestamp | `timestamp=792856380000` | `timestamp:792856380000` |
| jdet | `jdet=2449764.0791803706` | `jdet:2449764.0791803706` |
| jdut | `jdut=2449764.0784755815` | `jdut:2449764.0784755815` |
| utcdate | `utcdate=15|2|1995|13|53` | `utcdate:[15,2,1995,13,53]` |
| localdate | `localdate=15|2|1995|8|53` | `localdate:[15,2,1995,8,53]` |

For `localdate` to get the correct timezone, it should be used together with a correct [Location Parameter](/astrologico/param_location.html) for the city of New York, or used together with the [Options](/astrologico/param_options.html) parameter specifying New York's timezone.

<br><br><br>
