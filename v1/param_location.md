## Location Parameters

There are two Location parameters available, you only need to use one of them at a time. If none are used, the request will default to `0 0 0` and location-based date conversion will not work.

| Parameter | Type | Descripton |
|---|---|---|
| [location](#location) | Array | Indexed array of coordinates |
| querylocation | String | Search term to obtain coordinates. Can be localized by [Language](/astrologico/param_language.html) |

Using `querylocation` increases the request's total cost by 4.

<br>

### Location
{:id="location"}

| Index | Type | Required | Descripton |
|---|---|---|---|---|
| 0 | Float | yes | Latitude (decimal) |
| 1 | Float | yes | Longitude (decimal) |
| 2 | Float | no | Elevation (meters) \* |

\* Elevation is only needed for certain types of calculations (ie: topocentric coordinates) and may safely be omitted or set to 0 in most cases.

<br>

### Examples

Here's an example of how each parameter should be used to generate a chart for `February 15, 1995 - 1:53pm, in New York USA`. The second example sets elevation for topocentric coordinates. The third example increases the request's total cost by 4.

| Parameter | GET | POST
|---|---|---|
| location | `location=40.7127|-73.0059` | `location:[40.7127,-74.0059]` |
| location | `location=40.7127|-73.0059|30` | `location:[40.7127,-74.0059,30]` |
| querylocation | `querylocation=new york` | `querylocation:"new york"` |

<br><br><br>
