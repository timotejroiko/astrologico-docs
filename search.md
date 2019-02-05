---
layout: page
title: Endpoints - /v1/search
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
</style>

<br>

## Search

This endpoint is used to find the correct code points of supported objects, including planets, asteroids, stars, hypotheticals, arabic parts, and more

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| query | string | The search term |
| type | string | Optional. Filter results by object type |

<br>

### Object Types

| Type | Descripton |
|---|---|
| P | Planets, lunar nodes/apsides, and other objects |
| A | Asteroids |
| S | Stars |
| H | Hypothetical planets |
| L | Arabic parts/lots |

<br>

### Response Structure

| key | Type | Description |
|---|---|---|
| [STATUS](/astrologico/res_status.html) | string | Contains the response status |
| display | string | Number of isplayed results and total results |
| results | array | Array of results (max 100) |

<br>

### Result

| key | Type | Description |
|---|---|---|
| name | string | Object name |
| code | string | Object code point to use with other endpoints |
| type | string | Object type |
| formula | string | Arabic parts/lots only. The object formula |
| reverse | boolean | Arabic parts/lots only. Whether the formula is automatically reversed for night charts |

<br>

### Sample Response

```json
{
	"status": "OK",
	"display": "14 of 14",
	"results": [
		{
			"name": "Neris",
			"code": "A237845",
			"type": "asteroid"
		},
		{
			"name": "Eris",
			"code": "A136199",
			"type": "asteroid"
		},
		{
			"name": "Verish",
			"code": "A84225",
			"type": "asteroid"
		},
		{
			"name": "Amneris",
			"code": "A871",
			"type": "asteroid"
		},
		{
			"name": "Ronperison",
			"code": "A121633",
			"type": "asteroid"
		},
		{
			"name": "Eta Crateris",
			"code": "S459",
			"type": "star"
		},
		{
			"name": "Diannerister",
			"code": "A28688",
			"type": "asteroid"
		},
		{
			"name": "Zeta Crateris",
			"code": "S1090",
			"type": "star"
		},
		{
			"name": "Theta Crateris",
			"code": "S987",
			"type": "star"
		},
		{
			"name": "Gamma Crateris",
			"code": "S520",
			"type": "star"
		},
		{
			"name": "Epsilon Crateris",
			"code": "S395",
			"type": "star"
		},
		{
			"name": "Alkes / Alpha Crateris",
			"code": "S137",
			"type": "star"
		},
		{
			"name": "Labrum / Delta Crateris",
			"code": "S327",
			"type": "star"
		},
		{
			"name": "Alsharasif / Beta Crateris",
			"code": "S232",
			"type": "star"
		}
	]
}
```

<br><br><br>
