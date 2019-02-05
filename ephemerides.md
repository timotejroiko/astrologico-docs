---
layout: page
title: Endpoints - /v1/ephemerides
navigation: 4
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
	.inner code {
		font-size: 100%;
	}
</style>

<br>

## Ephemerides

The same as the [Chart](/astrologico/chart.html) endpoint but returns arrays of values, instead of single values, corresponding to a time range.

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| [Date Parameter](/astrologico/param_date.html) | - | Set date using one of the available date parameters. |
| [Location Parameter](/astrologico/param_location.html) | - | Set location using one of the available location parameters. |
| [range](/astrologico/param_range.html) | array | Set the time range for the ephemeris |
| [options](/astrologico/param_options.html) | array | Set calculation options |
| [display](/astrologico/param_display.html) | array | Set values to return |
| [planets](/astrologico/param_planets.html) | array | Set objects to display |
| [houses](/astrologico/param_houses.html) | string | Set house system to display |

<br>

### Response Structure

| key | Type | Description |
|---|---|---|
| [STATUS](/astrologico/res_status.html) | string | Contains the response status |
| [metadata](/astrologico/res_metadata.html) | object | Contains the configuration used for the calculations |
| [houses](/astrologico/res_houses.html) | object | Contains data for houses, returned only when a house system is selected |
| [planets](/astrologico/res_planets.html) | object | Contains data for planets |

<br><br><br>
