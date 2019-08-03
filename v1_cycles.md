---
layout: page
title: Endpoints - /v1/cycles
navigation: 3
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

## Cycles

This is endpoint is a standalone version of the [Return](/astrologico/param_return.html) parameter. It lets you examine the cycles of an object by finding the exact dates it returns to its original position. Only full returns are counted, repeated returns because of motion changes are ignored.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| <[Date](/astrologico/param_date.html)> | Number/Array | Set date using one of the available date parameters. |
| <[Location](/astrologico/param_location.html)> | Number/Array | Set location using one of the available location parameters. |
| [planet](/astrologico/param_planets.html) | String | Required. Object ID of the desired object |
| range | Number | Required. Amount of cycles to calculate (default 5, max 20) |
| reference | Number | Required. Reference/base chart in unix timestamp |
| [options](/astrologico/param_options.html) | Array | Set calculation options |
| [timezone](/astrologico/param_timezone.html) | String/Integer | Set timezone manually |
| [language](/astrologico/param_language.html) | String | Set language to localize certain functions |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | String | Contains the response status |
| [error](/astrologico/res_status.html) | String | Contains the error message in case of error |
| [date](/astrologico/res_metadata.html#date) | Object | Date and time information |
| [referenceDate](/astrologico/res_metadata.html#date) | Object | Reference date (base chart) |
| [result](#result) | Object | result object |
| [keyInfo](/astrologico/res_keyinfo.html) | Object | Contains data about your API key's usage and rate limits |

<br>

### Response - Result
{:id="result"}

| key | Type | Description |
|---|---|---|
| name | string | Object name |
| cycles | array | Array of [Date](/astrologico/res_metadata.html#date) objects |

<br>

## Sample request

Get the dates for the next 10 solar returns for a person born in timestamp `739847298374`, starting from `October 10, 2015`

```
GET

https://api.astrologico.org/v1/cycles?planet=P0&utcdate=10|10|2015&reference=739847298374&range=10&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/cycles",
header: {
	"Authorization": APIKEY
},
body: {
	"utcdate":[10,10,2015],
	"planet":"P0",
	"reference":739847298374,
	"range":10
}
```

<br>

## Sample response

```
{
	"status":"OK",
	"date":{
		"input":"utcdate",
		"calendar":"Gregorian",
		"accuracy":1,
		"ISO":"2015-10-10T12:00:00.000Z",
		"UNIX":1444478400000,
		"UTCDate":{
			"day":10,
			"month":10,
			"year":2015,
			"hour":12,
			"minute":0,
			"second":0,
			"milisecond":0
		},
		"JD":{
			"julianDayET":2457306.000789167,
			"julianDayUT":2457306.000002225
		},
		"siderealTime":"13:15:06",
		"obliquity":23.434798756661944,
		"sun":196.86409230694173,
		"moon":169.81132016348744,
		"ascendant":287.32335872298506
	},
	"referenceDate":{
		"input":"timestamp",
		"accuracy":5,
		"calendar":"Gregorian",
		"ISO":"1993-06-12T01:08:18.374Z",
		"UNIX":739847298374,
		"UTCDate":{
			"day":12,
			"month":6,
			"year":1993,
			"hour":1,
			"minute":8,
			"second":18,
			"milisecond":374
		},
		"JD":{
			"julianDayET":2449150.548119884,
			"julianDayUT":2449150.5474311314
		},
		"siderealTime":"18:29:48",
		"obliquity":23.439229310469667,
		"sun":81.09099125486739,
		"moon":349.05899550828366,
		"ascendant":8.115931525223065
	},
	"result":{
		"name":"Sun",
		"cycles":[
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2016-06-11T14:36:20.239Z",
				"UNIX":1465655780239,
				"UTCDate":{
					"day":11,
					"month":6,
					"year":2016,
					"hour":14,
					"minute":36,
					"second":20,
					"milisecond":239
				},
				"JD":{
					"julianDayET":2457551.109356748,
					"julianDayUT":2457551.108565936
				},
				"siderealTime":"07:57:47",
				"obliquity":23.434491704577677,
				"sun":81.09099125367099,
				"moon":162.87938193163433,
				"ascendant":211.60566574997145
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2017-06-11T20:29:37.306Z",
				"UNIX":1497212977306,
				"UTCDate":{
					"day":11,
					"month":6,
					"year":2017,
					"hour":20,
					"minute":29,
					"second":37,
					"milisecond":306
				},
				"JD":{
					"julianDayET":2457916.3547047456,
					"julianDayUT":2457916.353908715
				},
				"siderealTime":"13:51:05",
				"obliquity":23.43466700965333,
				"sun":81.09099125132362,
				"moon":286.34683209617947,
				"ascendant":295.7902016329718
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2018-06-12T02:17:21.127Z",
				"UNIX":1528769841127,
				"UTCDate":{
					"day":12,
					"month":6,
					"year":2018,
					"hour":2,
					"minute":17,
					"second":21,
					"milisecond":127
				},
				"JD":{
					"julianDayET":2458281.5961841554,
					"julianDayUT":2458281.59538446
				},
				"siderealTime":"19:38:48",
				"obliquity":23.43514094706243,
				"sun":81.09099124523158,
				"moon":57.21452490896792,
				"ascendant":26.62766728923103
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2019-06-12T07:55:40.073Z",
				"UNIX":1560326140073,
				"UTCDate":{
					"day":12,
					"month":6,
					"year":2019,
					"hour":7,
					"minute":55,
					"second":40,
					"milisecond":73
				},
				"JD":{
					"julianDayET":2458646.831133264,
					"julianDayUT":2458646.830331214
				},
				"siderealTime":"01:17:06",
				"obliquity":23.4358137603775,
				"sun":81.09099851583545,
				"moon":198.37530025908447,
				"ascendant":107.79006586958728
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2020-06-11T13:51:27.941Z",
				"UNIX":1591883487941,
				"UTCDate":{
					"day":11,
					"month":6,
					"year":2020,
					"hour":13,
					"minute":51,
					"second":27,
					"milisecond":941
				},
				"JD":{
					"julianDayET":2459012.0782074654,
					"julianDayUT":2459012.077401087
				},
				"siderealTime":"07:12:54",
				"obliquity":23.436521622508675,
				"sun":81.09099124760353,
				"moon":332.2251244805824,
				"ascendant":199.74255604700843
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2021-06-11T19:39:08.958Z",
				"UNIX":1623440348958,
				"UTCDate":{
					"day":11,
					"month":6,
					"year":2021,
					"hour":19,
					"minute":39,
					"second":8,
					"milisecond":958
				},
				"JD":{
					"julianDayET":2459377.3196665333,
					"julianDayUT":2459377.3188536805
				},
				"siderealTime":"13:00:35",
				"obliquity":23.437192097446143,
				"sun":81.09099124841298,
				"moon":96.16236791679624,
				"ascendant":283.94928697169587
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2022-06-12T01:16:32.205Z",
				"UNIX":1654996592205,
				"UTCDate":{
					"day":12,
					"month":6,
					"year":2022,
					"hour":1,
					"minute":16,
					"second":32,
					"milisecond":205
				},
				"JD":{
					"julianDayET":2459742.553969061,
					"julianDayUT":2459742.5531505207
				},
				"siderealTime":"18:37:57",
				"obliquity":23.437826673674095,
				"sun":81.0909912471405,
				"moon":226.9940101951956,
				"ascendant":10.323572518189547
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2023-06-12T07:08:56.805Z",
				"UNIX":1686553736805,
				"UTCDate":{
					"day":12,
					"month":6,
					"year":2023,
					"hour":7,
					"minute":8,
					"second":56,
					"milisecond":805
				},
				"JD":{
					"julianDayET":2460107.798704022,
					"julianDayUT":2460107.7978796875
				},
				"siderealTime":"00:30:22",
				"obliquity":23.438280071073336,
				"sun":81.09099125305656,
				"moon":10.18119926155439,
				"ascendant":96.97399512239986
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2024-06-11T12:55:48.485Z",
				"UNIX":1718110548485,
				"UTCDate":{
					"day":11,
					"month":6,
					"year":2024,
					"hour":12,
					"minute":55,
					"second":48,
					"milisecond":485
				},
				"JD":{
					"julianDayET":2460473.0395857347,
					"julianDayUT":2460473.0387556134
				},
				"siderealTime":"06:17:14",
				"obliquity":23.438431360162696,
				"sun":81.09099124858001,
				"moon":141.54482874897724,
				"ascendant":184.69552480440137
			},
			{
				"input":"utcdate",
				"calendar":"Gregorian",
				"accuracy":5,
				"ISO":"2025-06-11T18:47:58.796Z",
				"UNIX":1749667678796,
				"UTCDate":{
					"day":11,
					"month":6,
					"year":2025,
					"hour":18,
					"minute":47,
					"second":58,
					"milisecond":796
				},
				"JD":{
					"julianDayET":2460838.28415524,
					"julianDayUT":2460838.2833193983
				},
				"siderealTime":"12:09:25",
				"obliquity":23.438303280378566,
				"sun":81.09099125480309,
				"moon":266.33093738026133,
				"ascendant":272.1620380934794
			}
		]
	}
}
```

<br><br><br>
