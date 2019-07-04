---
layout: page
title: Parameters - Options
navigation: 5
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

## Options

An array of options to configure several chart generation settings, timezones, etc...

| option | Descripton |
|---|---|
| TRUEPOSITIONS | Return True positions instead of Apparent |
| HELIOCENTRIC | Return Heliocentric positions instead of Geocentric |
| TOPOCENTRIC | Return Topocentric positions instead of Geocentric |
| ASTROMETRIC | Astrometric positions (disable Aberration of Light and Gravitational Deflection) |
| JULIAN | Use Julian calendar instead of automatic |
| GREGORIAN | Use Gregorian calendar instead of automatic |
| UTCTOLOCAL | Return Local Date when input is a UTC date (becomes a `Type2` request) |

### Example

Create a heliocentric chart with true astrometric positions

| GET | POST |
|---|---|
|`options=TRUEPOSITIONS|ASTROMETRIC|HELIOCENTRIC`|`options:["TRUEPOSITIONS","ASTROMETRIC","HELIOCENTRIC"]`|

<br><br><br>
