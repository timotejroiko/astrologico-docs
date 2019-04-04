---
layout: page
title: Parameters - Houses
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

## Parameters - Houses

A house system number to display Houses, Ascendant, Midheaven and other related points.

| Number | House System |
|---|---|
| 0 | Alcabitus |
| 1 | APC |
| 2 | Axial Rotation / Meridian / Zariel |
| 3 | Azimuthal / Horizontal |
| 4 | Campanus |
| 5 | Carter / Poli-Equatorial |
| 6 | Equal (1st house = ascendant) |
| 7 | Equal (10th house = midheaven) |
| 8 | Equal (1st house = 0 aries) |
| 9 | Gauquelin Sectors |
| 10 | Sunshine / Makransky (solution Treindl) |
| 11 | Sunshine / Makransky (solution Makransky) |
| 12 | Koch |
| 13 | Krusinski / Pisa / Goelzer |
| 14 | Morinus |
| 15 | Placidus |
| 16 | Polich / Page / Topocentric |
| 17 | Porphyrius / Porphyry |
| 18 | Pullen SD (sinusoidal delta) / Neo-Porphyry |
| 19 | Pullen SR (sinusoidal ratio) |
| 20 | Regiomontanus |
| 21 | Sripati |
| 22 | Vehlow Equal (middle of 1st house = ascendant) |
| 23 | Whole Sign |

### Parameters - Houses Examples

Example for retrieving houses, Ascendant, Midheaven and other related points using Placidus:

| GET | POST |
|---|---|
|`houses=15`|`houses:15`|

<br><br><br>
