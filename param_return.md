---
layout: page
title: Parameters - Return
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

## Return

An indexed array to create a "Return" chart from the [Date](/astrologico/param_date.html) parameter, by finding a nearby date an object returns to its exact original position. It requires a reference/base chart in a unix timestamp format.

| Index | Type | Descripton |
|---|---|---|
| 0 | integer | Reference chart timestamp |
| 1 | string | Object ID |
| 2 | string | "closest", "current" or "next" |

<br>

### Examples

|GET|POST|Description|
|---|---|---|
|`return=739847298374|P0|closest`|`options:[739847298374,"P0","closest"]`| Closest Solar Return for a person born in timestamp 739847298374 |
|`return=739847298374|P5|next`|`options:[739847298374,"P5","next"]`| Next Jupiter Return for a person born in timestamp 739847298374 |
|`return=739847298374|P1|current`|`options:[739847298374,"P1","current"]`| Previous Lunar Return (currently active) for a person born in timestamp 739847298374 |

<br><br><br>