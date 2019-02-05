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

| Parameter | Type | Default | Descripton |
|---|---|---|---|
| [Date](/astrologico/param_date.html) | multi | no | current date | A [date](test) parameter. If none is supplied, the current date is used. |
| [Location](/astrologico/param_location.html) | multi | no |  | A [location](test) parameter |

^

| Parameter | Type | Default | Descripton |
| date parameters |
| timestamp | number | current date | Set date using a unix timestamp |
| jdet | number | current date | Set date using Julian Day Ephemeris Time |
| jdut | number | current date | Set date using Julian Day Univeral Time |
| utcdate | array | current date | Set date using day,month,year,hour,minute,second in UTC |
| localdate | array | current date | Set date using day,month,year,hour,minute,second in local time |
| location parameters |
| location | array | [0,0,0] | Set location using longitude,latitude,elevation in decimal coordinates |
| querylocation | array | [] | Set location using a search string |
| other parameters |
| timestamp | number | current date | A unix timestamp |
| timestamp | number | current date | A unix timestamp |
| timestamp | number | current date | A unix timestamp |

<br><br><br>
