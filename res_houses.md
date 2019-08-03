---
layout: page
title: Response - Houses
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

<script>
	window.onload = function(){
		if (location.hash) {
			let target = location.hash;
			document.querySelector(".content").scroll({top:document.querySelector(target).offsetTop,behavior:"smooth"})
		}
	}
</script>

<br>

## Houses

The houses field contains the calculated data for all the house cusps and angles using the house system specified in [Houses](/astrologico/param_houses.html).

| Value | Type | Descripton |
|---|---|
| [houses](#houses) | Object | Object containing house cusps data |
| [ascendant](/astrologico/res_data.html) | Object | Ascendant |
| [mc](/astrologico/res_data.html) | Object | MC (midheaven / medium coeli) |
| [armc](/astrologico/res_data.html) | Object | ARMC (right rscencion of the midheaven) |
| [vertex](/astrologico/res_data.html) | Object | Vertex |
| [equatorialAscendant](/astrologico/res_data.html) | Object | Equatorial Ascendant |
| [kochCoAscendant](/astrologico/res_data.html) | Object | Koch co-Ascendant |
| [munkaseyCoAscendant](/astrologico/res_data.html) | Object | Munkasey co-Ascendant |
| [munkaseyPolarAscendant](/astrologico/res_data.html) | Object | Munkasey Polar Ascendant |
| error | String | error message* |

\* If an error occurs, an error message is displayed here and no other fields are returned.

<br>

### Houses - Houses
{:id="houses"}

The inner houses field contains the calculated house cusps for the selected house system. When using Gauquelin Sectors the number of house cusps returned is 36 instead of 12, and the house cusps are clockwise instead of counterclockwise.

| Value | Type | Descripton |
|---|---|
| [house1](/astrologico/res_data.html) | Object | 1st house |
| [house2](/astrologico/res_data.html) | Object | 2nd house |
| [house3](/astrologico/res_data.html) | Object | 3rd house |
| ... | Object | etc... |

<br><br><br>
