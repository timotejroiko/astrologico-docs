---
layout: page
title: Parameters - Timezone
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

## Timezone

Timezone can be manually specified using either an offset in minutes or a timezone string according to the [tz-database specification](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

| Parameter | Type | Descripton |
|---|---|---|---|
| timezone | string/number | timezone string or offset minutes |

Examples:

| GET | POST | Descripton |
|---|---|---|
| `timezone=America/New_York` | `timezone:"America/New_York"` | Set timezone to America/New_York (UTC-5 or UTC-4) |
| `timezone=300` | `timezone:300` | Set timezone to +300 minutes (UTC+5) |
| `timezone=-120` | `timezone:-120` | Set timezone to -120 minutes (UTC-2) |

<br><br><br>
