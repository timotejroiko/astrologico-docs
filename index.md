---
layout: page
title: Getting Started
navigation: 1
---


# Astrologico API

Astrologico API is a fully featured microservice for retrieving astrological calculations and data. All endpoints are `HTTPS` only and available via `GET` and `POST`. Automated key generation is currently not available but you can request a key at our [Discord server (https://discord.gg/jtaCURK)](https://discord.gg/jtaCURK)

The API's base url is `https://api.astrologico.org`. 



## GET vs POST

There are two differences between `GET` requests and `POST` requests. In `GET` requests, array parameters should be pipe-delimited query strings, and the API key should be a query-string as well. In `POST` requests, array parameters should be JSON arrays, and the API key should be in the `Authorization` header.

| GET  | POST |
| --- | --- |
| ?field=value1\|value2\|value3&key=APIKEY  | header: {Authorization:APIKEY},body: {field:[value1,value2,value3]}  |



## Rate Limits & Request Type

Depending on the endpoint and the parameters used, a request can become a `type1` request or a `type2` request. `type1` requests are simpler and have higher rate limits, while `type2` requests require more resources, and as such have lower rate limits.

When the rate limits are reached, subsequent requests will have a 5 second delay added to them before a response is returned. Our API will continue to be available even if you go over our rate limits, but we advise you to upgrade your key to avoid slowing down your application.

Our current Rate limits are as follows:

| Type1  | Type2 |
| --- | --- |
| 250/day | 50/day |


## Sample requests

```
GET

https://api.astrologico.org/chart?utcdate=25|10|2003|12|30|0&location=51.5074|0.1278&planets=P0|P1|P2
```
