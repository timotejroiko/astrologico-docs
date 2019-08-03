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

## Return

An indexed array to create a "Return" chart from the [Date](/astrologico/param_date.html) parameter, by finding the nearest dates an object returns to its exact original position. It requires a reference/base chart in a unix timestamp format.

| Index | Type | Descripton |
|---|---|---|
| 0 | Integer | Reference chart timestamp |
| 1 | String | Object ID |
| 2 | String | "closest", "current" or "next" |

<br>

### Examples

Creating a Solar Return chart for a person born in timestamp `739847298374` (12 Jun 1993 01:08:18 GMT).

|GET|POST|Description|
|---|---|---|
|`return=739847298374|P0|closest`|`options:[739847298374,"P0","closest"]`| Closest Solar Return |
|`return=739847298374|P5|next`|`options:[739847298374,"P5","next"]`| Next Jupiter Return |
|`return=739847298374|P1|current`|`options:[739847298374,"P1","current"]`| Previous (current) Lunar Return |

<br><br><br>