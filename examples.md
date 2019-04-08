---
layout: page
title: Usage Examples
navigation: 7
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

### Usage Examples - Western Chart

Casting a western chart for `June 25th 1994 at 18:30 (6:30pm) in Miami, Florida` using `Placidus` houses, local time and location by name.

Omitting `planets` will return a default selection as mentioned in [Planets](/astrologico/param_planets.html).

Because `localdate` and/or `querylocation` are used, this is a `Type2` request.

```
GET

https://api.astrologico.org/v1/chart?localdate=25|6|1994|18|30&querylocation=miami florida&houses=15&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/chart",
header: {
	"Authorization": APIKEY
},
body: {
	"localdate":[25,6,1994,18,30],
	"querylocation":"miami florida",
	"houses":15
}
```

<br>

### Usage Examples - Vedic Chart

Casting a "vedic" chart for `May 14th 1987 at 8:43 (8:43am) in London, United Kingdom` using only classic planets plus "mean" rahu & ketu, `Whole Signs` houses, Lahiri sidereal zodiac, UTC time and location by coordinates.

Because neither `localdate` nor `querylocation` are used, this is a `Type1` request.

```
GET

https://api.astrologico.org/v1/chart?utcdate=14|5|1987|8|43&location=51.509865|0.118092&planets=P0|P1|P2|P3|P4|P5|P6|P10|P23&houses=23&options=sidereal:1&key=APIKEY
```

```
POST

url: "https://api.astrologico.org/v1/chart",
header: {
	"Authorization": APIKEY
},
body: {
	"utcdate":[14,5,1987,8,43],
	"location":[51.509865,0.118092],
	"houses":23,
	"options":["sidereal:1"],
	"planets":["P0","P1","P2","P3","P4","P5","P6""P10","P23"]
}
```

<br>

### Usage Examples - Human Design System

Casting a "human design system" chart for `December 1st 2001 at 21:21 (9:21pm) in Lisbon, Portugal` using local time and location by name.

Since a human design combines two charts, it requires multiple requests to be made. This example uses 1 `Type2` and 2 `Type1` requests.

```
GET

https://api.astrologico.org/v1/chart?localdate=14|5|1987|8|43&querylocation=lisbon portugal&planets=P0|P14|P1|P2|P3|P4|P5|P6|P7|P8|P9|P11|P24&display=hds&key=APIKEY

https://api.astrologico.org/v1/designdate?utcdate=UTC-DATE-RECEIVED-FROM-FIRST-REQUEST&0location=COORDINATES-RECEIVED-FROM-FIRST-REQUEST&key=APIKEY

https://api.astrologico.org/v1/chart?utcdate=UTC-DATE-RECEIVED-FROM-SECOND-REQUEST&location=COORDINATES-RECEIVED-FROM-FIRST-REQUEST&planets=P0|P14|P1|P2|P3|P4|P5|P6|P7|P8|P9|P11|P24&key=APIKEY

```

```
POST

{
	url: "https://api.astrologico.org/v1/chart",
	header: {
		"Authorization": APIKEY
	},
	body: {
		"localdate":[14,5,1987,8,43],
		"querylocation":"lisbon portugal",
		"planets":["P0","P14","P1","P2","P3","P4","P5","P6","P7","P8","P9","P11","P24"],
		"display":["hds"]
	}
}

{
	url: "https://api.astrologico.org/v1/designdate",
	header: {
		"Authorization": APIKEY
	},
	body: {
		"utcdate":UTC-DATE-RECEIVED-FROM-FIRST-REQUEST,
		"location":COORDINATES-RECEIVED-FROM-FIRST-REQUEST
	}
}

{
	url: "https://api.astrologico.org/v1/chart",
	header: {
		"Authorization": APIKEY
	},
	body: {
		"utcdate":UTC-DATE-RECEIVED-FROM-SECOND-REQUEST,
		"location":COORDINATES-RECEIVED-FROM-FIRST-REQUEST,
		"planets":["P0","P14","P1","P2","P3","P4","P5","P6","P7","P8","P9","P11","P24"],
		"display":["hds"]
	}
}
```

<br>

### Usage Examples - Zodiac Sign Degrees

All longitudes are returned in 360 decimal degrees. The easiest way to get zodiac signs and degrees is to use the modulo operator present in most programming languages.

To obtain degrees, minutes and seconds, some further math is required. here's a simple javascript example.

```js
let longitude = planets.P0.longitude; // longitude received form the api, ie: 265.78468274
let zodiac = ["aries","taurus","gemini","cancer","leo","virgo","libra","scorpio","sagittarius","capricorn","aquarius","pisces"]; // list of zodiac signs
let sign = zodiac[Math.floor(longitude / 30)]; // get correct zodiac sign
let signdegree = longitude % 30; // get zodiac sign decimal degree
console.log(signdegree+" degrees "+sign) // 25.78468274 degrees sagittarius

// simplified example on how to obtain, degrees minutes and seconds
let degree = Math.floor(signdegree);
let minute = Math.floor(signdegree % 1 * 60);
let second = Math.floor(signdegree * 60 % 1 * 60);
console.log(degree+"° "+minute+"' "+second+"''") // 25° 47' 4''
```

<br><br><br>