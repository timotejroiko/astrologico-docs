## Key Info

This object contains information about your API key, its current usage, daily limits, etc... It is disabled by default and can be enabled in the [Options](parameters_options.md) parameter.

| Value | Type | Descripton |
|---|---|---|
| cost | Integer | The request's total cost |
| limit | Integer | The key's daily limit |
| usage | Integer | The key's current daily usage |
| remaining | Integer | The key's remaining daily usage |
| nextReset | Integer | Amount of time until the next usage reset (in milliseconds) |
| limitExpires | Integer | The timestamp at which the key's daily limit expires (0 = never) |

<br>