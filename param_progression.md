---
layout: page
title: Parameters - Progression
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

## Progression

An indexed array to create a "Progressed" chart from the [Date](/astrologico/param_date.html) parameter. It requires a reference/base chart in a unix timestamp format.

| Index | Type | Descripton |
|---|---|---|
| 0 | Integer | Reference chart timestamp |
| 1 | Integer | Progression method for planets |
| 2 | Integer | Progression method for angles |

<br>

### Progression - Methods

| Progression method for planets | Descripton |
|---|---|
| 1 | Secondary Progression (1 day = 1 year) |
| 2 | Tertiary Progression (1 day = 1 lunar cycle)|
| 3 | Minor Progression (1 lunar cycle = 1 year)|
| 4 | Secondary Return (secondary progressed solar return) |
| 5 | Primary Directions (1 day = 4 minutes) |

| Progression method for angles | Descripton |
|---|---|
| 1 | Solar Arc in Longitude (1 progressed degree = 1 degree) |
| 2 | Solar Arc in Right Ascension (1 progressed degree = 1 degree) |
| 3 | Naibod in Longitude (1 year = 0'59''08 degrees) |
| 4 | Naibod in Right Ascension (1 year = 0'59''08 degrees) |
| 5 | Primary Directions (1 year = 1 degree) |
| 6 | Secondary MC (1 progressed degree = 1 geographical degree) |
| 7 | Daily Houses / Mean Quotian (1 year = 366 degrees) |

<br>

### Examples

Creating a Progressed chart for a person born in timestamp `739847298374` (12 Jun 1993 01:08:18 GMT).

|GET|POST|Description|
|---|---|---|
|`progression=739847298374|1|7`|`progression:[739847298374,1,7]`| Progressed chart using Secondary progressions and Daily Houses |
|`progression=739847298374|5|5`|`progression:[739847298374,5,5]`| Progressed chart using Primary Directions |

<br><br><br>