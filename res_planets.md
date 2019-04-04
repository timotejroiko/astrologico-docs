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
		padding: 5px;
	}
	@media (min-width: 745px) {
		.sidebar {
			width: 30%;
		}
	}
</style>

<br>

## Response - Planets

The planets field contains all the calculated planetary data organized by code points.

| Value | Type | Descripton |
|---|---|
| [code point](astrologico/res_data.html) | object | Object containing planetary data for the specified object |
| ... | object | etc... |

For example, the code point for the Sun is `P0`, the response for the sun data will be:

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
