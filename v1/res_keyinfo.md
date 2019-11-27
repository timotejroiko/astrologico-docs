---
layout: page
title: Response - Key Info
navigation: 6
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

## Key Info

This object contains information about your API key, its current usage, daily limits, etc... It is disabled by default and can be enabled in the [Options](/astrologico/param_options.html) parameter.

| Value | Type | Descripton |
|---|---|
| cost | Integer | The request's total cost |
| limit | Integer | The key's daily limit |
| usage | Integer | The key's current daily usage |
| remaining | Integer | The key's remaining daily usage |
| nextReset | Integer | Amount of time until the next usage reset (in milliseconds) |
| limitExpires | Integer | The timestamp at which the key's daily limit expires (0 = never) |

<br><br><br>