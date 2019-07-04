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
		padding: 5px;
	}
	@media (min-width: 745px) {
		.sidebar {
			width: 30%;
		}
	}
</style>

<br>

## Progression

An indexed array to create a "Progressed" chart from the [Date](/astrologico/param_date.html) parameter. It requires a reference/base chart in a unix timestamp format.

| Index | Type | Descripton |
|---|---|---|
| 0 | integer | Reference chart timestamp |
| 1 | integer | Progression method for planets |
| 2 | integer | Progression method for angles |

<br>

### Progression - Methods

| Progression method for planets | Descripton |
|---|---|
| 1 | Secondary Progression |
| 2 | Tertiary Progression |
| 3 | Minor Progression |
| 4 | Secondary Return |
| 5 | Primary Directions |

| Progression method for angles | Descripton |
|---|---|
| 1 | Solar Arc in Longitude |
| 2 | Solar Arc in Right Ascension |
| 3 | Naibod in Longitude |
| 4 | Naibod in Right Ascension |
| 5 | Primary Directions |
| 6 | Secondary MC |
| 7 | Daily Houses / Mean Quotian |

<br>

### Examples

|GET|POST|Description|
|---|---|---|
|`progression=739847298374|1|7`|`progression:[739847298374,1,7]`| Progressed chart using Secondary progressions and Daily Houses for a person born in timestamp 739847298374 |
|`progression=739847298374|5|5`|`progression:[739847298374,5,5]`| Progressed chart using Primary Directions for a person born in timestamp 739847298374 |

<br><br><br>