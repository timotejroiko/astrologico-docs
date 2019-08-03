---
layout: page
title: Parameters - Stations
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

## Stations

When `STATIONS` are enabled in [Display](/astrologico/param_display.html), `true` is returned if the object is within 1 day of its zero point (point where it switches directions). This array changes that behavior and redefines when an object should be considered "Stationary".

| Index | Type | Descripton |
|---|---|---|
| 0 | Float | Number |
| 1 | String | Option |

Stations currently support the following options in index 1:

| Option | Description |
|---|---|
| "days" | Index 0 becomes number of days from zero |
| "%"" | Index 0 becomes percentage of average speed |

<br>

### Examples

|GET Example|POST Example|Description|
|---|---|---|
|`stations=2|days`|`stations:[2,"days"]`| Consider an object "stationary" if within 2 days of its zero point |
|`stations=3|%`|`stations:[3,"%"]`| Consider an object "stationary" if its speed is below 3% of its absolute average speed that year |

<br><br><br>