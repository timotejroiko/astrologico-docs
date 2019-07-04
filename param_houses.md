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

## Houses

A house system ID to display Houses, Ascendant, Midheaven and other related points.

| ID | House System |
|---|---|
| 1 | Alcabitus |
| 2 | APC |
| 3 | Axial Rotation / Meridian / Zariel |
| 4 | Azimuthal / Horizontal |
| 5 | Campanus |
| 6 | Carter / Poli-Equatorial |
| 7 | Equal (1st house = ascendant) |
| 8 | Equal (10th house = midheaven) |
| 9 | Equal (1st house = 0 aries) |
| 10 | Gauquelin Sectors |
| 11 | Sunshine / Makransky (solution Treindl) |
| 12 | Sunshine / Makransky (solution Makransky) |
| 13 | Koch |
| 14 | Krusinski / Pisa / Goelzer |
| 15 | Morinus |
| 16 | Placidus |
| 17 | Polich / Page / Topocentric |
| 18 | Porphyrius / Porphyry |
| 19 | Pullen SD (sinusoidal delta) / Neo-Porphyry |
| 20 | Pullen SR (sinusoidal ratio) |
| 21 | Regiomontanus |
| 22 | Sripati |
| 23 | Vehlow Equal (middle of 1st house = ascendant) |
| 24 | Whole Sign |

### Example

Retrieving houses, Ascendant, Midheaven and other related points using Placidus:

| GET | POST |
|---|---|
|`houses=16`|`houses:16`|

<br><br><br>
