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
		padding: 0.3vh;
	}
	.sidebar {
		min-width: 300px;
	}
	.sidebar .sidebar-main {
	    height: calc(100% - 50px);
	    overflow-y: auto;
	}
</style>

<br>

## Endpoints

These are the currently available and also future endpoints:

| Endpoint | Description | Request Type
|---|---|---|
| [/v1/chart](/astrologico/chart.html) | Astrological data for a given time and place, including planets, houses, stars, and other objects | Type1/Type2 \* |
| [/v1/ephemeris](/astrologico/ephemeris.html) |  Astrological data for a time range. Returns arrays of values instead of single values | Type2 |
| [/v1/search](/astrologico/search.html) | Search for objects by name | Type1 |
| [/v1/dateconversion](/astrologico/dateconversion.html) | Convert between local and universal time in multiple formats | Type2 |
| [/v1/location](/astrologico/location.html) | Find coordinates by location name (geocoding) | Type2 |
| [/v1/speeds](/astrologico/motion.html) | View an object's average speeds during a given year | Type2 |
| [/v1/cycles](/astrologico/cycles.html) | View the dates an object returns to its original position | Type2 |

| /v1/motion (soon) | Find the dates an object changes motion | Type2 |
| /v1/findtransit (soon) | Find the dates an object reaches a certain position | Type2 |
| /v1/findaspect (soon) | Find the dates an object forms a specific aspect with another objecy | Type2 |
| /v1/scanpoint (soon) | Find all objects in a specific position | Type2 |

\* becomes a Type2 request if certain settings are enabled

<br><br><br>
