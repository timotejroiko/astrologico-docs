---
layout: page
title: Response - Status
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
		padding: 5px;
	}
	@media (min-width: 745px) {
		.sidebar {
			width: 30%;
		}
	}
</style>

<br>

## Response - Status

All requests return a `status` field which contains one of the following string values:

| Value | Descripton |
|---|---|
| OK | Request completed successfully |
| RATELIMIT | Rate limit has been reached and the request was throttled |
| ERROR | An error occured and the request was interrupted |

If `status` returns `ERROR`, an aditional `error` field will be returned with a brief description of the issue. Example:

```
{
	"status": "ERROR",
	"error": "invalid date - day must be from 1 to 31"
}
```

Occasionally when our server goes through changes or updates, a small downtime can be expected (usually about 1-2 seconds at a time). In such cases, the following error message is be returned but you can safely have your application automatically retry the request:

```
{
	"status": "ERROR",
	"error": "temporarily unavailable"
}
```

<br><br><br>
