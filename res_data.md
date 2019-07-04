---
layout: page
title: Response - Data
navigation: 6
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

## Data

This object contains all the calculated data. These can be enabled by using [Display Options](/astrologico/param_display.html).

All fields (except `name`, `formula` and `error`) are arrays when using the `ephemeris` endpoint.

| Value | Type | Descripton |
|---|---|
| name | string | Object name |
| formula | string | Object's formula (arabic parts only) |
| reversed | string | Whether the formula was reversed (arabic parts only) |
| longitude | float | The object's ecliptic longitude in decimal degrees |
| latitude | float | The object's ecliptic latitude in decimal degrees |
| distance | float | The object's distance in AU |
| longitudeSpeed | float | The object's longitude speed in decimal degrees per day |
| latitudeSpeed | float | The object's latitude speed in decimal degrees per day |
| distanceSpeed | float | The object's distance changes in AU per day |
| hds | string | The objects gate, line, color, tone and base position for the Human Design System |
| stationary | boolean | Whether the object is considered "stationary" |
| declination | float | The object's celestial declination in decimal degrees |
| rightAscension | float | The object's right ascension in decimal degrees |
| declinationSpeed | float | The object's declination speed in decimal degrees per day |
| rightAscensionSpeed | float | The object's right ascension speed in decimal degrees per day |
| magnitude | float | The object's magnitude |
| angularDiameter | float | The object's angular diameter in decimal degrees |
| azimuth | float | The object's azimuth decimal degrees |
| altitude | float | The object's altitude in decimal degrees |
| error | string | error message |

Not all objects return all of the above, some are exclusive to certain objects while others might not be available to certain objects. In case a field is not available, it will return `"not available"` instead.

<br><br><br>