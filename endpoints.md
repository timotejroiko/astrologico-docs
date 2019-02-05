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
</style>

<br>

## Endpoints

These are the currently available endpoints

| Endpoint | Description | Request Type
|---|---|---|
| [/v1/chart](/astrologico/chart.html) | Astrological data for a given time and place, including planets, houses, stars, and other objects | Type1/Type2 |
| [/v1/ephemeris](/astrologico/ephemeris.html) |  Astrological data for a time range. Returns arrays of values instead of single values | Type2 |
| /v1/search | Find object information by name | Type1 |
| /v1/dateconversion | Date conversion between local time, utc time, julian dates and unix timestamps | Type2 |
| /v1/location | Find coordinates by name (geocoding) | Type2 |
| /v1/designdate | Find the design date for human design system charts | Type1/Type2 |
| /v1/zeropoint | Find the direction switch date of an object | Type2 |
| /v1/cycles | Find the return date of an object | Type2 |

<br><br><br>
