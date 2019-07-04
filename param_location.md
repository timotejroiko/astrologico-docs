---
layout: page
title: Parameters - Location
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

<script>
	window.onload = function(){
		if (location.hash) {
			let target = location.hash;
			document.querySelector(".content").scroll({top:document.querySelector(target).offsetTop,behavior:"smooth"})
		}
	}
</script>

<br>

## Location Parameters

There are two Location parameters which are mutually exclusive, you only need to use one of them. If none are used, the request will default to Latitude 0, Longitude 0, Elevation 0.

| Parameter | Type | Descripton |
|---|---|---|
| [location](#location) | array | Indexed array of coordinates |
| querylocation | string | Search term to obtain coordinates |

Using `querylocation` turns the request into a `Type2` request.

<br>

### Location
{:id="location"}

| Index | Type | Required | Default | Descripton |
|---|---|---|---|---|
| 0 | Float | yes | 0 | Latitude (decimal) |
| 1 | Float | yes | 0 | Longitude (decimal) |
| 2 | Float | no | 0 | Elevation (meters) * |

\* Elevation is only needed for certain types of calculations (ie: topocentric coordinates) and may safely be omitted or set to 0 in most cases.

<br>

### Examples

Here's an example of how each parameter should be used to generate a chart for `February 15, 1995 - 1:53pm, in New York USA`

| Parameter | GET | POST
|---|---|---|
| location | `location=40.7127|-73.0059|30` | `location:[40.7127,-74.0059,30]` |
| querylocation | `querylocation=new york` | `querylocation:"new york"` |

<br><br><br>
