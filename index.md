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
	.sidebar {
		width: 30%
	}
	.navigation li {
		padding: 5px;
	}
</style>

<br>

# Astrologico API (beta)

Astrologico API is a fully featured microservice for retrieving astrological calculations and data. All endpoints are `HTTPS` only and available via `GET` or `POST`. The API is nearly production ready but we encourage you to experiment with it and help us weed out any remaining bugs, inconsistencies or incorrect data. You can get and API key at our [Discord server](https://discord.gg/jtaCURK){:target="_blank"}

The API's base url is `https://api.astrologico.org`.

<br>
  
## GET vs POST

There are two differences between `GET` and `POST` requests. In `GET` requests, array parameters should be pipe-delimited query strings, and the API key should be a query-string as well. In `POST` requests, array parameters should be JSON arrays, and the API key should be in the `Authorization` header.

| GET  | POST |
| --- | --- |
| ?field=value1\|value2\|value3&key=APIKEY  | header: { Authorization: APIKEY },<br>body: { field: [value1,value2,value3] } |

<br>

## Request Type & Rate Limits

Depending on the endpoint and the parameters used, a request can become a `type1` request or a `type2` request. `type1` requests are simpler and require less resources, while `type2` requests require more resources and as such have lower rate limits.

When the limits are hit, subsequent requests will have a scaling delay added to them before a response is returned. Our API will continue to be available even if you go over our rate limits, but we advise you to upgrade your key to avoid slowing down your application. Limits reset at midnight UTC.

Our current Rate limits are as follows:

| Type1  | Type2 |
| --- | --- |
| 250/day | 50/day |

Premium options and pricing for higher rate limits will be available soon.

<br><br><br>
