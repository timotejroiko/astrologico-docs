---
layout: page
title: Getting Started
navigation: 1
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
	@media (max-width: 745px) {
		.sidebar .sidebar-main {
		    height: calc(100% - 320px);
		}
	}
</style>

<br>

# Astrologico API (beta)

Astrologico API is a fully featured microservice for retrieving astrological calculations and data. All endpoints are `HTTPS` only and available via `GET` or `POST`. The API is nearly production ready and we encourage you to experiment with it and help us weed out any remaining bugs, inconsistencies or incorrect data. You can get an API key at our [Discord server](https://discord.gg/jtaCURK){:target="_blank"}

The API's base url is `https://api.astrologico.org`.

<br>

## Features

Astrologico API's features include:

* Covers a time range of over 20000 years
* Built-in date, time and location converters
* Tropical and sidereal zodiacs, over 40 ayanamsas and the ability to define custom ayanamsas
* Over 20 astrological house systems
* Derived data such as persona charts and the human design system
* Progressed charts with several different methods
* Solar Returns and Returns for other objects
* Specialized tools such as stations, motion changes, aspect/transit lookup, ephemerides and more
* Includes major planets, hypothetical planets, over 500000 asteroids, over 100 arabic parts/lots, Planetary Nodes, Apsides and more
* Over 7000 built-in stars and access to millions of stars and stellar objects through our integration with the simbad database
* Several types of information including Longitude, Latitude, Declination, Right Ascension, Altitude, Azimuth, Distance, Speeds, Human Design and more

<br>
  
## GET vs POST

There are two differences between `GET` and `POST` requests. In `GET` requests, array parameters should be pipe-delimited query strings, and the API key should be a query-string as well. In `POST` requests, array parameters should be JSON arrays, and the API key should be in an `Authorization` header.

| GET  | POST |
| --- | --- |
| ?field=value1\|value2\|value3&key=APIKEY  | header: { Authorization: APIKEY },<br>body: { field: [value1,value2,value3] } |

<br>

## Request Type, Rate Limits & Pricing

Depending on the endpoint and the parameters used, a request can be `type1` or `type2`. `type1` requests require less resources, while `type2` requests require more resources and as such have lower rate limits.

When the limits are hit, subsequent requests will have a scaling delay added to them before a response is returned. Our API will continue to be available even if you go over our rate limits, but we advise you to upgrade your key to avoid slowing down your application. Limits reset at midnight UTC.

Our current Rate limits are as follows:

| Pricing | Type1  | Type2 |
| --- | --- | --- |
| Free | 250/day | 50/day |

Premium options and pricing for higher rate limits will be available soon.

<br><br><br>
