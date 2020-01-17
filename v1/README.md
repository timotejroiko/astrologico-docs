## Astrologico API v1 (Beta)

This is the official documentation for the version 1 of the API. This version has been through extensive private testing and is now ready for public testing. Version 1 will remain available for experimental use and small projects but keep an eye out for the upcoming Version 2 of the API.

For any questions, bug reports, etc... feel free to contact us via [Discord](https://discord.gg/jtaCURK) or [Github](https://github.com/timotejroiko/astrologico-docs).

<br>

### Getting Started

Astrologico API is a fully featured microservice capable of retrieving planetary positions, astrological calculations and other data. All endpoints are `HTTPS` only and available via `GET` or `POST`. We encourage you to experiment with it and help us weed out any remaining bugs, inconsistencies or incorrect information. Astrologico API requires an API key which can be obtained at our [Discord server](https://discord.gg/jtaCURK) or by contacting us.

By using this service, you agree to our [Terms and Conditions](https://astrologico.org/terms);

<br>

### Features

Astrologico API version 1's features include:

* Covers a time range of 30000 years for planets and 6000 years for asteroids
* Built-in date, time and location converters
* Tropical and sidereal zodiacs, over 40 built-in ayanamsas plus customizable ayanamsas
* Over 20 built-in house systems plus ability to derive houses from RAMC
* Derived charts such as "persona" charts and the "human design system"
* Progressed charts in several different progression methods
* Solar Returns and Returns for other objects
* Includes all major planets, hypothetical planets, over 1000 comets, over 500000 asteroids, over 100 arabic parts/lots, Planetary Nodes, Apsides and more
* Over 7000 built-in stars, plus access to millions of stars and stellar objects through our integration with the simbad database
* Available data includes Longitude, Latitude, Declination, Right Ascension, Altitude, Azimuth, Distance, Speeds, Human Design hexagrams and more

<br>
  
### GET vs POST

There are two differences between `GET` and `POST` requests. In `GET` requests, arrays should be given as pipe-delimited query strings, and the API key should be in a query-string as well. In `POST` requests the API key should be given in an `Authorization` header.

| GET  | POST |
| --- | --- |
| ?field=value1\|value2\|value3&key=APIKEY  | header: { Authorization: APIKEY },<br>body: { field: [value1,value2,value3] } |

<br>

### Cost, Rate Limits & Pricing

Depending on the endpoint and the parameters used, a request will have a given `cost` based on complexity and resource usage. Each day you will be given a usage limit, and when the limit is reached, subsequent requests will be increasingly throttled. Our API will continue to be available even if you go over our rate limits, but we advise you to upgrade your key to avoid slowing down your application. Limits reset at midnight UTC.

Our current Rate limits are as follows:

| Pricing | Daily Limit |
| --- | --- |
| Free | 300 |

Options and pricing for higher rate limits will be available later on down the road.

<br>