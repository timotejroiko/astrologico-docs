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

When [Display](/astrologico/param_display.html) includes Stations, `true` is returned if the object is within 1 day of its zero point (when it switches directions). This option can be used to change when an object should be considered "Stationary". Stations support number of days from zero and percentage from average speed.

|GET Example|POST Example|Description|
|---|---|---|
|`stations=2|days`|`options:[2,"days"]`| Consider an object "stationary" if within 2 days of its zero point |
|`stations=3|%`|`options:[3,"%"]`| Consider an object "stationary" if its speed is below 3% of its absolute average speed that year |

<br><br><br>