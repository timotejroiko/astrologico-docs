## Date Parameters

There are several Date parameters available, you only need to use one of them at a time. If none are used, the request will default to the current date and time.

| Parameter | Type | Input Type | Descripton
|---|---|---|---|
| timestamp | Integer | UTC | Unix timestamp in milliseconds |
| jdet | Float | UTC | Julian day in ephemeris time or terrestrial time |
| jdut | Float | UTC | Julian day in universal time |
| [utcdate](#datearray) | Array | UTC | Indexed date/time array in UTC |
| [localdate](#datearray) | Array | LOCAL | Indexed date/time array in local time |

Using `localdate` increases the request's total cost by 2.

<br>

### utcdate & localdate
{:id="datearray"}

| Index | Type | Required | Default | Descripton |
|---|---|---|---|---|
| 0 | Integer | yes | - | Day |
| 1 | Integer | yes | - | Month |
| 2 | Integer | yes | - | Full Year |
| 3 | Integer | no | 12 | Hour (in 24h format) |
| 4 | Integer | no | 0 | minute |
| 5 | Float | no | 0 | second and millisecond |

The `localdate` parameter requires a [Location Parameter](/astrologico/param_location.html) or a [Timezone](/astrologico/param_timezone) parameter to obtain the required timezone. If none are found, it defaults to UTC. Using `localdate` increases the request's total cost by 2.

<br>

### Examples

Here's an example of how each parameter should be used to generate a chart for `February 15, 1995 - 1:53pm (local time), in New York City`

| Parameter | GET | POST
|---|---|---|
| timestamp | `timestamp=792856380000` | `timestamp:792856380000` |
| jdet | `jdet=2449764.0791803706` | `jdet:2449764.0791803706` |
| jdut | `jdut=2449764.0784755815` | `jdut:2449764.0784755815` |
| utcdate | `utcdate=15|2|1995|18|53` | `utcdate:[15,2,1995,18,53]` |
| localdate | `localdate=15|2|1995|13|53` | `localdate:[15,2,1995,13,53]` |

For `localdate` to get the correct timezone, it should be used together with a correct [Location Parameter](/astrologico/param_location.html) for the city of New York, or used together with the [Timezone](/astrologico/param_timezone) parameter specifying New York's timezone.

<br><br><br>
