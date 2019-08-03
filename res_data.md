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

All fields (except `name`, `formula` and `error`) are arrays when using the [Ephemeris](/astrologico/v1_ephemeris.html) endpoint.

| Value | Type | Descripton |
|---|---|
| name | String | Object name |
| names | Array | Array of names for objects with multiple names (returned instead of `name` for stars and arabic parts only) |
| designations | Array | Array of official designations (returned for stars only) |
| formula | String | Object's formula (arabic parts only) |
| reversed | String | Whether the formula was reversed (arabic parts only) |
| longitude | Float | The object's ecliptic longitude in decimal degrees |
| latitude | Float | The object's ecliptic latitude in decimal degrees |
| distance | Float | The object's distance in AU |
| longitudeSpeed | Float | The object's longitude speed in decimal degrees per day |
| latitudeSpeed | Float | The object's latitude speed in decimal degrees per day |
| distanceSpeed | Float | The object's distance changes in AU per day |
| hds | String | The object's gate, line, color, tone and base position for the Human Design System |
| stationary | Boolean | Whether the object is considered "stationary" |
| declination | Float | The object's celestial declination in decimal degrees |
| rightAscension | Float | The object's right ascension in decimal degrees |
| declinationSpeed | Float | The object's declination speed in decimal degrees per day |
| rightAscensionSpeed | Float | The object's right ascension speed in decimal degrees per day |
| magnitude | Float | The object's magnitude |
| angularDiameter | Float | The object's angular diameter in decimal degrees |
| azimuth | Float | The object's azimuth decimal degrees |
| altitude | Float | The object's altitude in decimal degrees |
| error | String | error message (if an error occurs) |

Not all objects support all display options, some are exclusive to certain objects while others might not be available to certain objects. In case a field is not available, it will return `"not available"` instead.

<br><br><br>