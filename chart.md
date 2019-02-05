---
layout: page
title: /v1/chart
navigation: 3
---

<br>

## Chart

This is the primary endpoint through which you can retrieve everything you need to generate accurate astrological charts of various types.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|---|
| Date Parameter | - | A [date](test) parameter. If none is supplied, the current date is used. |
| Location Parameter | - | A [location](test) parameter |



| timestamp* | number | current date | Unix timestamp |
| jdet* | number | current date | Julian Day Ephemeris Time |
| jdut* | number | current date | Julian Day Univeral Time |
| utcdate* | array | current date | Date array in UTC |
| localdate* | array | current date | Date array in Local Time. Requires location or timezone options |
| location** | array | [0,0,0] | Location array |
| querylocation** | array | [0,0,0] | location |
| timestamp | number | current date | A unix timestamp |
| timestamp | number | current date | A unix timestamp |
| timestamp | number | current date | A unix timestamp |

<br><br><br>
