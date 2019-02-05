---
layout: page
title: /v1/chart
navigation: 3
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
</style>

<br>

## Chart

This is the primary endpoint through which you can retrieve everything you need to generate accurate astrological charts of various types.

### Parameters

| Parameter | Type | Descripton |
| timestamp | number | Set date using a unix timestamp |
| jdet | number | Set date using Julian Day Ephemeris Time |
| jdut | number | Set date using Julian Day Univeral Time |
| utcdate | array | Set date using UTC date and time |
| localdate | array | Set date using local date and time |
| location | array | Set location using decimal coordinates |
| querylocation | array | Set location using a search string |
| options | array | Set calculation options |
| display | array | Set values to return |
| planets | array | Set objects to calculate |
| houses | string | Set house system and display houses |

<br><br><br>
