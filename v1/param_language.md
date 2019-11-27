---
layout: page
title: Parameters - Language
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

## Language

Sets the language to localize certain functions using a 2-digit language code.

| Type | Descripton |
|---|---|
| String | language code in `ISO 639-1` format |

The following functions and values can be localized:

| Field | Kind | Descripton |
|---|---|---|
| [querylocation](/astrologico/param_location.html#querylocation) | Parameter | Localized search \* |
| [queryResult](/astrologico/res_metadata.html#location) | Response | Localized result |
| [name](/astrologico/res_metadata.html#tz) | Response | Localized Timezone name |

\* A localized querylocation request allows for language-specific searches, for example searching for `rome` in English will return `Rome, Italy` but searching for `rome` in Italian will return `Rome, Georgia, Stati Uniti d'America` (Rome, Georgia, United States).

<br>

### Examples

Set language to Italian, allowing for location searches using Italian terms and names as well as returning location and timezone results in Italian.

| GET | POST | Descripton |
|---|---|---|
| `language=it` | `language:"it"` | Set language to Italian |

<br><br><br>
