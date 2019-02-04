---
layout: page
title: Getting Started
navigation: 1
---


# Astrologico API

Astrologico API is a fully featured microservice for retrieving astrological calculations and data. All endpoints are `HTTPS` only and available via `GET` and `POST`. Automated key generation is currently not available but you can request a key at our __[Discord server (https://discord.gg/jtaCURK)](https://discord.gg/jtaCURK)__

The API's base url is `https://api.astrologico.org`. 

## GET vs POST

Most parameters are identical between `GET` requests and `POST` requests, except for array parameters, which have the following difference:

| GET  | POST |
| ------------- | ------------- |
| ?key=value1|value2|value3  | key:[value1,value2,value3]  |

## Request Type
