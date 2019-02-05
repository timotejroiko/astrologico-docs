---
layout: page
title: /v1/chart
navigation: 3
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
</style>

<br>

## Chart

This is the primary endpoint through which you can retrieve everything you need to generate accurate astrological charts of various types. All parameters are optional, check each parameter's documentation for default values and additional information.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| [[Date Parameter]](/astrologico/param_date.html) | - | Set date using one of the available date parameters. |
| [[Location Parameter]](/astrologico/param_location.html) | - | Set location using one of the available location parameters. |
| [options](/astrologico/param_options.html) | array | Set calculation options |
| [display](/astrologico/param_display.html) | array | Set values to return |
| [planets](/astrologico/param_planets.html) | array | Set objects to display |
| [houses](/astrologico/param_houses.html) | string | Set house system to display |

<br>

### Response Structure

| key | Type | Description |
|---|---|---|
| STATUS | string | Contains `OK`, `ERROR` or `RATELIMITED` |
| ERROR | string | Error message, returned only when STATUS is `ERROR` |
| [metadata](/astrologico/res_metadata.html) | object | Contains the date, location and options used |
| [houses](/astrologico/res_houses.html) | object | Contains data for houses, returned only when a house system is selected |
| [planets](/astrologico/res_planets.html) | object | Contains data for planets |

<br><br><br>
