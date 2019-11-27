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

# Astrologico API (beta)

Astrologico API is a fully featured microservice for retrieving astrological calculations and data. All endpoints are `HTTPS` only and available via `GET` or `POST`. The API is nearly production ready and we encourage you to experiment with it and help us weed out any remaining bugs, inconsistencies or incorrect data. You can get an API key at our [Discord server](https://discord.gg/jtaCURK){:target="_blank"}

By using this service, you agree to our [Terms and Conditions](#) (coming soon);

<br>

## Features

Astrologico API's features include:

* Covers a time range of 30000 years for planets and 6000 years for asteroids
* Built-in date, time and location converters
* Tropical and sidereal zodiacs, over 40 built-in ayanamsas and customizable ayanamsas
* Over 20 built-in astrological house systems and ability to derive houses from RAMC
* Derived charts such as "persona" charts and the "human design system"
* Progressed charts with several different methods
* Solar Returns and Returns for other objects
* Specialized tools such as stations, cycles, motions, aspect/transit lookups, ephemerides and more
* Includes major planets, hypothetical planets, over 1000 comets, over 500000 asteroids, over 100 arabic parts/lots, Planetary Nodes, Apsides and more
* Over 7000 built-in stars, plus access to millions of stars and stellar objects through our integration with the simbad database
* Several types of information including Longitude, Latitude, Declination, Right Ascension, Altitude, Azimuth, Distance, Speeds, I-Ching hexagrams/gates and more

<br>
  
## GET vs POST

There are two differences between `GET` and `POST` requests. In `GET` requests, arrays should be given as pipe-delimited query strings, and the API key should be in a query-string as well. In `POST` requests the API key should be given in an `Authorization` header.

| GET  | POST |
| --- | --- |
| ?field=value1\|value2\|value3&key=APIKEY  | header: { Authorization: APIKEY },<br>body: { field: [value1,value2,value3] } |

<br>

## Cost, Rate Limits & Pricing

Depending on the endpoint and the parameters used, a request will have a given `cost` based on complexity and resource usage. Each day you will be given a usage limit, and when the limit is reached, subsequent requests will be increasingly throttled. Our API will continue to be available even if you go over our rate limits, but we advise you to upgrade your key to avoid slowing down your application. Limits reset at midnight UTC.

Our current Rate limits are as follows:

| Pricing | Daily Limit |
| --- | --- |
| Free | 500 |

Options and pricing for higher rate limits will be available soon.

<br><br><br>
