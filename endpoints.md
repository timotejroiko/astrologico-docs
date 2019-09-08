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
	@media (max-width: 745px) {
		.sidebar .sidebar-main {
		    height: calc(100% - 320px);
		}
	}
</style>

<br>

## Endpoints

Here is a list of the currently available endpoints.

The API's base url is `https://api.astrologico.org`.

| Endpoint | Description | Base Cost
|---|---|---|
| [/v1/chart](/astrologico/v1_chart.html) | Astrological data for a given time and place, including planets, houses, stars, and other objects | 2 |
| [/v1/ephemeris](/astrologico/v1_ephemeris.html) |  Astrological data for a time range. Returns arrays of values instead of single values | 10 |
| [/v1/search](/astrologico/v1_search.html) | Search for objects by name | 1 |
| [/v1/dateconversion](/astrologico/v1_dateconversion.html) | Convert between local and universal time in multiple formats | 2 |
| [/v1/location](/astrologico/v1_location.html) | Find coordinates by location name (geocoding) | 4 |
| [/v1/velocity](/astrologico/v1_velocity.html) | View an object's average speeds and motion during a given year | 6 |
| [/v1/cycles](/astrologico/v1_cycles.html) | Find the dates an object returns to its original position | 8 |
| [/v1/scanner](/astrologico/v1_scanner.html) | Scans a point in the sky and returns all objects found | 25 |

<!--
| /v1/motion (soon) | Find the dates an object changes motion | Type2 |
| /v1/findtransit (soon) | Find the dates an object reaches a certain position | Type2 |
| /v1/findaspect (soon) | Find the dates an object forms a specific aspect with another objecy | Type2 |

-->

Some endpoints have additional costs based on the parameters used.

<br><br><br>
