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
	.sidebar {
		width: 30%
	}
	.navigation li {
		padding: 5px;
	}
</style>

<script>
	if (location.hash) {
		let target = location.hash;
		window.scrollTop = document.querySelector(target).offsetTop;
	}
</script>

<br>

## Parameters - Location Parameters

There are two Location parameters which are mutually exclusive, you only need to use one of them. If none are used, the request will default to Longitude 0, Latitude 0, Elevation 0.

| Parameter | Type | Descripton |
|---|---|---|---|
| [location](#location) | array | Sorted coordinates array |
| querylocation | string | Search term to obtain coordinates |

Using `querylocation` turns the request into a `Type2` request.

<br>

### Parameters - Location
{:id="location"}

| Index | Type | Required | Default | Descripton |
|---|---|---|---|---|
| 0 | Float | yes | 0 | Longitude (decimal) |
| 1 | Float | yes | 0 | Latitude (decimal) |
| 2 | Float | no | 0 | Elevation (meters) |

<br><br><br>
