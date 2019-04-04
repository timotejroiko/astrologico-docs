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

## Endpoints

These are the currently available and also future endpoints:

| Endpoint | Description | Request Type
|---|---|---|
| [/v1/chart](/astrologico/chart.html) | Astrological data for a given time and place, including planets, houses, stars, and other objects | Type1/Type2* |
| [/v1/ephemerides](/astrologico/ephemerides.html) |  Astrological data for a time range. Returns arrays of values instead of single values | Type2 |
| [/v1/search](/astrologico/search.html) | Find object information by name | Type1 |
| [/v1/dateconversion](/astrologico/dateconversion.html) | Date conversion between local time, utc time, julian dates and unix timestamps | Type2 |
| [/v1/location](/astrologico/location.html) | Find coordinates by location name (geocoding) | Type2 |
| [/v1/designdate](/astrologico/designdate.html) | Find the design date for human design system charts | Type1/Type2* |
| /v1/zeropoint (soon) | Find the date an object changes motion | Type2 |
| /v1/cycles (soon) | Find the date an object returns to its original position | Type2 |
| /v1/findtransit (soon) | Find the date an object reaches a certain position | Type2 |
| /v1/averagespeed (soon) | Find an object's average speed during a specific year | Type2 |

\* becomes a Type2 request if one of the following parameters is used:<br>`localdate` `querylocation` `options=utctolocal`

<br><br><br>
