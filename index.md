---
layout: page
title: Getting Started
navigation: 1
---


# Astrologico API

Astrologico API is a fully featured microservice for retrieving astrological calculations and data. All endpoints are `HTTPS` only and available via `GET` and `POST`. Automated key generation is currently not available but you can request a key at our [Discord server (https://discord.gg/jtaCURK)](https://discord.gg/jtaCURK)

The API's base url is `https://api.astrologico.org`. 



## GET vs POST

Most parameters are identical between `GET` requests and `POST` requests, except for array parameters, which have the following difference:

| GET  | POST |
| ------------- | ------------- |
| ?key=value1\|value2\|value3  | key:[value1,value2,value3]  |



## Rate Limits & Request Type

Depending on the endpoint and the parameters used, a request can become a `type1` request or a `type2` request. `type1` requests are simpler and have higher rate limits, while `type2` requests require more resources, and as such have lower rate limits.

When the rate limits are reached, subsequent requests will have a 5 second delay added to them before a response is returned. Our API will continue to be available even if you go over our rate limits, but we advise you to upgrade your key to avoid slowing down your application.

Our current Rate limits are as follows:

| Type1  | Type2 |
| ------------- | ------------- |
| 250/day | 50/day |





