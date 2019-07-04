---
layout: page
title: Parameters - Sidereal
navigation: 5
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
	.sidebar .sidebar-main {
	    height: calc(100% - 50px);
	    overflow-y: scroll;
	}
</style>

<br>

## Sidereal

The Sidereal option can be used to create sidreal and vedic charts. It offers several built in Ayanamsas, as well as an option to set a custom Ayanamsa.

| N | Type | Ayanamsa |
|---|---|---|
| 1 | Integer | Fagan/Bradley |
| 2 | Integer | Lahiri |
| 3 | Integer | De Luce |
| 4 | Integer | Raman |
| 5 | Integer | Usha/Shashi |
| 6 | Integer | Krishnamurti |
| 7 | Integer | Djwhal Khul |
| 8 | Integer | Yukteshwar |
| 9 | Integer | J.N. Bhasin |
| 10 | Integer | Babylonian/Kugler 1 |
| 11 | Integer | Babylonian/Kugler 2 |
| 12 | Integer | Babylonian/Kugler 3 |
| 13 | Integer | Babylonian/Huber |
| 14 | Integer | Babylonian/Eta Piscium |
| 15 | Integer | Babylonian/Aldebaran = 15 Taurus |
| 16 | Integer | Hipparchos |
| 17 | Integer | Sassanian |
| 18 | Integer | Galactic Center = 0 Sagittarius |
| 19 | Integer | J2000 |
| 20 | Integer | J1900 |
| 21 | Integer | B1950 |
| 22 | Integer | Suryasiddhanta |
| 23 | Integer | Suryasiddhanta (mean Sun) |
| 24 | Integer | Aryabhata |
| 25 | Integer | Aryabhata (mean Sun) |
| 26 | Integer | SS Revati |
| 27 | Integer | SS Citra |
| 28 | Integer | True Citra |
| 29 | Integer | True Revati |
| 30 | Integer | True Pushya (PVR Narasimha Rao) |
| 31 | Integer | Galactic Center (Gil Brand) |
| 32 | Integer | Galactic Equator (IAU1958) |
| 33 | Integer | Galactic Equator |
| 34 | Integer | Galactic Equator mid-Mula |
| 35 | Integer | Skydram (Mardyks) |
| 36 | Integer | True Mula (Chandra Hari) |
| 37 | Integer | Dhruva / Galactic Center / Mula (Wilhelm) |
| 38 | Integer | Aryabhata 522 |
| 39 | Integer | Babylonian/Britton |
| 40 | Integer | Vedic/Sheoran |
| 41 | Integer | Cochrane/Galactic Center = 0 Capricorn |
| 42 | Integer | Galactic Equator (Fiorenza) |
| 43 | Integer | Vettius Valens |
| [reference,initial] | Array | Custom Ayanamsa |

A custom ayanamsa can be set by specifying a reference date and an initial value. Reference date should be in Julian Days ET/TT (Ephemeris/Terrestrial Time) and the initial value should be the Ayanamsa value in decimal (number of degrees difference from Tropical)

<br>

### Example

|GET|POST|Description|
|---|---|---|
|`sidereal=6`|`sidereal:6`|Set Ayanamsa to Krishnamurti|
|`sidereal=2451545|25.5`|`sidereal:[2451545,25.5]`|Set Ayanamsa to 25.5 (25 deg 30 min) degrees at julian day 2451545 (J2000 / noon of January 1st, 2000)|

<br><br><br>