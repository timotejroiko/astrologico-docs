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
		padding: 5px;
	}
	@media (min-width: 745px) {
		.sidebar {
			width: 30%;
		}
	}
</style>

<br>

## Response - Data

This object contains all the calculated data. These can be enabled by using [Display Options](/astrologico/param_display.html).

| Value | Type | Descripton |
|---|---|
| name | string | Object name (not returned for houses) |
| formula | string | Object's formula * |
| reversed | string | Whether the formula was reversed * |
| longitude | float | The object's ecliptic longitude in decimal degrees |
| latitude | float | The object's ecliptic latitude in decimal degrees **** |
| distance | float | The object's distance in AU **** |
| longitudeSpeed | float | The object's longitude speed in decimal degrees per day ** |
| latitudeSpeed | float | The object's latitude speed in decimal degrees per day ** **** |
| distanceSpeed | float | The object's distance changes in AU per day ** **** |
| hds | string | The objects gate, line, color, tone and base position for the Human Design System |
| stationary | boolean | Whether the object is considered "stationary" ** *** |
| declination | float | The object's celestial declination in decimal degrees |
| rightAscension | float | The object's right ascension in decimal degrees |
| declinationSpeed | float | The object's declination speed in decimal degrees per day ** ***** |
| rightAscensionSpeed | float | The object's right ascension speed in decimal degrees per day ** |
| magnitude | float | The object's magnitude ** *** ****** |
| angularDiameter | float | The object's angular diameter in decimal degrees ** *** ****** |
| azimuth | float | The object's azimuth decimal degrees |
| altitude | float | The object's altitude in decimal degrees |

\* returned only for arabic parts (always enabled)

\*\* not returned for arabic parts

\*\*\* not returned for houses

\*\*\*\* always 0 for houses

\*\*\*\*\* returns full traveled distance for houses, ie: goes to down to -23 and up to +23 in one day.

\*\*\*\*\*\* always 0 for non-physical objects, in addition, angularDiameter is always 0 for stars.

<br><br><br>
