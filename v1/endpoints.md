## Endpoints

Here is a list of the currently available endpoints.

v1's base url is `https://api.astrologico.org/v1`.

| Endpoint | Description | Base Cost
|---|---|---|
| [chart](chart.md) | Astrological data for a given time and place, including planets, houses, stars, and other objects | 2 |
| [ephemeris](ephemeris.md) |  Astrological data for a given time range. Same as `chart` but returns arrays of values instead | 10 |
| [search](search.md) | Search for available objects by name | 1 |
| [dateconversion](date.md) | Convert between multiple date and time formats | 2 |
| [location](location.md) | Find geographical coordinates by location name (geocoding) | 4 |
| [velocity](velocity.md) | View an object's average speeds and statistics for a given year | 8 |
| [find](transit.md) | Finds the exact dates an object arrives at a specific position | 8 |
| [scan](scanner.md) | Scans a point in the sky and returns all available objects found | 50 |

Some endpoints have additional costs based on the parameters used.