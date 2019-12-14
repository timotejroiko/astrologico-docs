## Return

An indexed array to create a "Return" chart from the [Date](parameters_date.md) parameter, by finding the nearest dates an object returns to its exact original position. It requires a reference/base chart in a unix timestamp format. Returns increase the request's total cost by 1.

| Index | Type | Descripton |
|---|---|---|
| 0 | Integer | Reference chart timestamp |
| 1 | String | Object ID |
| 2 | String | "closest", "current" or "next" |

<br>

### Examples

Creating a Solar Return chart for a person born in timestamp `739847298374` (12 Jun 1993 01:08:18 GMT).

|GET|POST|Description|
|---|---|---|
|return=739847298374\|P0\|closest|return:[739847298374,"P0","closest"]| Closest Solar Return |
|return=739847298374\|P5\|next|return:[739847298374,"P5","next"]| Next Jupiter Return |
|return=739847298374\|P1\|current|return:[739847298374,"P1","current"]| Previous (current) Lunar Return |

<br>