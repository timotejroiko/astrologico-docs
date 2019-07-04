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
		padding: 0.3vh;
	}
	.sidebar .sidebar-main {
	    height: calc(100% - 50px);
	    overflow-y: scroll;
	}
</style>

<br>

### Western Chart

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

### Vedic Chart

Casting a "vedic" chart for `May 14th 1987 at 8:43 (8:43am) in London, United Kingdom` using only traditional planets, "mean" rahu & ketu, `Whole Signs` houses, Lahiri sidereal zodiac, UTC time and location by coordinates.

Because neither `localdate` nor `querylocation` are used, this is a `Type1` request.

```
GET

https://api.astrologico.org/v1/chart?utcdate=14|5|1987|8|43&location=51.509865|0.118092&planets=P0|P1|P2|P3|P4|P5|P6|P10|P23&houses=23&sidereal=2&key=APIKEY
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
	"sidereal":2,
	"planets":["P0","P1","P2","P3","P4","P5","P6""P10","P23"]
}
```

<br>

### Human Design System

Casting a "human design system" chart for `December 1st 2001 at 21:21 (9:21pm) in Lisbon, Portugal` using local time and location by name.

Since a human design combines two charts, it requires multiple requests to be made. To avoid using multiple `Type2` requests, you can use some converted information returned from the first request in the second one.

```
GET

https://api.astrologico.org/v1/chart?localdate=14|5|1987|8|43&querylocation=lisbon portugal&planets=P0|P14|P1|P2|P3|P4|P5|P6|P7|P8|P9|P11|P24&display=hds&key=APIKEY

https://api.astrologico.org/v1/chart?timestamp=TIMESTAMP_RECEIVED_FROM_FIRST_REQUEST&location=COORDINATES_RECEIVED_FROM_FIRST_REQUEST&planets=P0|P14|P1|P2|P3|P4|P5|P6|P7|P8|P9|P11|P24&display=hds&derived=hds|1&key=APIKEY

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
	url: "https://api.astrologico.org/v1/chart",
	header: {
		"Authorization": APIKEY
	},
	body: {
		"timestamp":TIMESTAMP_RECEIVED_FROM_FIRST_REQUEST,
		"location":COORDINATES_RECEIVED_FROM_FIRST_REQUEST,
		"planets":["P0","P14","P1","P2","P3","P4","P5","P6","P7","P8","P9","P11","P24"],
		"derived":["hds",1]
		"display":["hds"]
	}
}
```

<br>

### Solar Return Chart

Casting a "solar return" chart for the year `2015` in `New York USA` for a person born in `June 24th 1967 at 9:34 (9:24am) in Paris, France` using local time and location by name. This chart requires a reference date which should be provided as a timestamp, so the base chart must be calculated first in order to obtain it.

Both requests are `Type2` because they are using `querylocation`

```
GET

https://api.astrologico.org/v1/chart?localdate=24|6|1967|9|34&querylocation=paris france&key=APIKEY

https://api.astrologico.org/v1/chart?utcdate=24|6|2015&querylocation=new york usa&return=TIMESTAMP_RECEIVED_FROM_FIRST_REQUEST|P0|closest&key=APIKEY
```

```
POST

{
	url: "https://api.astrologico.org/v1/chart",
	header: {
		"Authorization": APIKEY
	},
	body: {
		"localdate":[24,6,1967,9,34],
		"querylocation":"paris france"
	}
}

{
	url: "https://api.astrologico.org/v1/chart",
	header: {
		"Authorization": APIKEY
	},
	body: {
		"utcdate":[24,6,2015],
		"querylocation":"new york usa",
		"return":[TIMESTAMP_RECEIVED_FROM_FIRST_REQUEST,"P0","closest"]
	}
}
```

<br>

### Zodiac Signs and Degrees

All longitudes are returned in 360 decimal degrees. The easiest way to get zodiac signs and degrees is to use the modulo/modulus operator present in most programming languages.

To obtain degrees, minutes and seconds, some further math is required. here's a simple javascript example.

```js
// get the longitude received form the api, in this example the value is 265.78468274
let longitude = planets.P0.longitude; // 265.78468274

// list the zodiac signs in the correct order
let zodiac = ["aries","taurus","gemini","cancer","leo","virgo","libra","scorpio","sagittarius","capricorn","aquarius","pisces"];

// get the index for the correct zodiac sign by dividing and flooring the longitude value
let index = Math.floor(longitude / 30); // 8
let sign = zodiac[index]; // sagittarius

// get zodiac sign degree using modulo
let signdegree = longitude % 30; // 25.78468274

// this will output: 25.78468274 degrees sagittarius
console.log(signdegree + " degrees " + sign);

// to obtain degrees minutes and seconds some further math is required
let degree = Math.floor(signdegree); // 25
let minute = Math.floor(signdegree % 1 * 60); // 47
let second = Math.floor(signdegree * 60 % 1 * 60); // 4

// this will output: 25° 47' 4''
console.log(degree + "° " + minute + "' " + second + "''");
```

<br><br><br>