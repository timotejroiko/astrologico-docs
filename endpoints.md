---
layout: page
title: Endpoints
navigation: 2
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
	.inner code {
		font-size: 100%;
	}
</style>

<br>

## Endpoints

These are the currently available endpoints

| Endpoint | Description | Request Type
|---|---|---|
| [/v1/chart](/astrologico/chart.html) | Astrological data for a given time and place, including planets, houses, stars, and other objects | Type1/Type2* |
| [/v1/ephemeris](/astrologico/ephemeris.html) |  Astrological data for a time range. Returns arrays of values instead of single values | Type2 |
| [/v1/search](/astrologico/search.html) | Find object information by name | Type1 |
| [/v1/dateconversion](/astrologico/dateconversion.html) | Date conversion between local time, utc time, julian dates and unix timestamps | Type2 |
| [/v1/location](/astrologico/location.html) | Find coordinates by name (geocoding) | Type2 |
| [/v1/designdate](/astrologico/designdate.html) | Find the design date for human design system charts | Type1/Type2** |
| [/v1/zeropoint](/astrologico/zeropoint.html) | Find the direction switch date of an object | Type2 |
| [/v1/cycles](/astrologico/cycles.html) | Find the return date of an object | Type2 |

\* becomes a Type2 request if one of the following parameters is used:<br>`localdate` `querylocation` `options=utctolocal`
^
\*\* becomes a Type2 request if a mode other than `mode=0` is used

<br><br><br>
