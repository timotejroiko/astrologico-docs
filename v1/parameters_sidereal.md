## Sidereal

The Sidereal option creates charts with the Sidereal zodiac used in several types of Astrology. It offers several built in Ayanamsas, as well as an option to set a custom Ayanamsa.

| Type | Descripton |
|---|---|
| Integer/Array | Built-in Ayanamsa ID or array of values for custom Ayanamsa |

<br>

### Sidereal - Built-in Ayanamsas

| ID | Ayanamsa |
|---|---|
| 1 | Fagan/Bradley |
| 2 | Lahiri |
| 3 | De Luce |
| 4 | Raman |
| 5 | Usha/Shashi |
| 6 | Krishnamurti |
| 7 | Djwhal Khul |
| 8 | Yukteshwar |
| 9 | J.N. Bhasin |
| 10 | Babylonian/Kugler 1 |
| 11 | Babylonian/Kugler 2 |
| 12 | Babylonian/Kugler 3 |
| 13 | Babylonian/Huber |
| 14 | Babylonian/Eta Piscium |
| 15 | Babylonian/Aldebaran = 15 Taurus |
| 16 | Hipparchos |
| 17 | Sassanian |
| 18 | Galactic Center = 0 Sagittarius |
| 19 | J2000 |
| 20 | J1900 |
| 21 | B1950 |
| 22 | Suryasiddhanta |
| 23 | Suryasiddhanta (mean Sun) |
| 24 | Aryabhata |
| 25 | Aryabhata (mean Sun) |
| 26 | SS Revati |
| 27 | SS Citra |
| 28 | True Citra |
| 29 | True Revati |
| 30 | True Pushya (PVR Narasimha Rao) |
| 31 | Galactic Center (Gil Brand) |
| 32 | Galactic Equator (IAU1958) |
| 33 | Galactic Equator |
| 34 | Galactic Equator mid-Mula |
| 35 | Skydram (Mardyks) |
| 36 | True Mula (Chandra Hari) |
| 37 | Dhruva / Galactic Center / Mula (Wilhelm) |
| 38 | Aryabhata 522 |
| 39 | Babylonian/Britton |
| 40 | Vedic/Sheoran |
| 41 | Cochrane/Galactic Center = 0 Capricorn |
| 42 | Galactic Equator (Fiorenza) |
| 43 | Vettius Valens |
| 44 | Sheratan = 2°15' Aries |
| 45 | Vasilis Kanatas |

<br>

### Sidereal - Custom Ayanamsas

A custom ayanamsa can be set by specifying an array, instead of an integer, containing a reference date and an initial value. Reference date should be in Julian Days ET/TT (Ephemeris/Terrestrial Time) and the initial value should be the Ayanamsa value in decimal degrees (degree difference from the Tropical zodiac).

| Index | Type | Descripton |
|---|---|---|
| 0 | Float | Reference date in Julian Days |
| 1 | Float | Ayanamsa initial value in decimal degrees |

<br>

### Examples

|GET|POST|Description|
|---|---|---|
|sidereal=6|sidereal:6|Set Ayanamsa to Krishnamurti|
|sidereal=2451545\|25.5|sidereal:[2451545,25.5]|Set Ayanamsa to 25.5 degrees (25 deg 30 min) at julian day 2451545 (J2000 / noon of January 1st, 2000)|

<br>