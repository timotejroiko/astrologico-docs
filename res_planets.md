---
layout: page
title: Response - Planets
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
</style>

<br>

## Planets

The planets field contains all the calculated planetary data organized by Object IDs.

| Value | Type | Descripton |
|---|---|
| [Object ID](astrologico/res_data.html) | object | Object containing planetary data for the specified object |
| ... | object | etc... |

For example, the ID for the Sun is `P0`, the response for the sun data will be:

```
{
	"planets": {
		"P0": {
			//planetary data for the Sun
		}
	}
}
```

<br><br><br>
