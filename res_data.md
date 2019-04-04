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

This object contains all the calculated data for each requested value.

| Value | Type | Descripton |
|---|---|
| name | string | Object name (not returned for houses) |
| formula | string | Object's formula (returned only for arabic parts) |
| reversed | string | Whether the formula was reversed (returned only for arabic parts) |
| longitude | float | The object's ecliptic longitude in decimal degrees |
| latitude | float | The object's ecliptic latitude in decimal degrees (always 0 for houses) |
| distance | float | The object's distance in AU (always 0 for houses and arabic parts) |
| longitudeSpeed | float | The object's longitude speed in decimal degrees per day (not returned for arabic parts) |
| latitudeSpeed | float | The object's latitude speed in decimal degrees per day (always 0 for houses, not returned for arabic parts) |
| distanceSpeed | float | The object's distance changes in AU per day (always 0 for houses, not returned for arabic parts) |
| hds | string | The objects gate, line, color, tone and base position for the Human Design System |
| stationary | boolean | Whether the object is considered "stationary" (not returned for houses and arabic parts) |
| declination | float | The object's celestial declination in decimal degrees |
| rightAscension | float | The object's right ascension in decimal degrees |
| declinationSpeed | float | The object's declination speed in decimal degrees per day (not returned arabic parts) |
| rightAscensionSpeed | float | The object's right ascension speed in decimal degrees per day (not returned arabic parts) |
| magnitude | float | The object's magnitude (always 0 for hypotheticals, apsides and special points, not returned for houses and arabic parts) |
| angularDiameter | float | The object's angular diameter in decimal degrees (always 0 for stars, hypotheticals, apsides and special points, not returned for houses arabic parts) |
| azimuth | float | The object's azimuth decimal degrees |
| altitude | float | The object's altitude in decimal degrees |

<br><br><br>
