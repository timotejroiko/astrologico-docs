---
layout: page
title: Parameters - Planets
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
		padding: 5px;
	}
	@media (min-width: 745px) {
		.sidebar {
			width: 30%;
		}
	}
</style>

<br>

## Planets

An array of IDs specifying the objects that should be calculated. The ID format consists of a type identifier followed by an object number.
If omitted, it defaults to `P0 P1 P2 P3 P4 P5 P6 P7 P8 P9 P11`.

| Example | Descripton |
|---|---|
|P0|Planet number 0 (sun)|
|S1351|Star number 1351 (regulus)|
|A3|Asteroid number 3 (juno)|

<br>

### Object Type

| Object Type | Descripton |
|---|---|
| P | Planets and special objects |
| A | Asteroids |
| S | Stars |
| H | Hypothetical Planets |
| AP | Planet's Aphelion |
| AA | Asteroid's Aphelion |
| PP | Planet's Perihelion |
| PA | Asteroid's Perihelion |
| NP | Planet's Ascending Node |
| NA | Asteroid's Ascending Node |
| SP | Planet's Descending Node |
| SA | Asteroid's Descending Node |
| FP | Planet's Second Focus |
| FA | Asteroid's Second Focus |
| L | Arabic parts/lots |
| DL | Arabic parts/lots day (no reverse) |
| NL | Arabic parts/lots night (force reverse) |
| QS: | Get an object from the simbad database |

<br>

### Main IDs

Asteroid IDs follow the same numbering as their official designation. Other objects are either numbered alphabetically or follow a special order, but you can use the [Search](/astrologico/search.html) endpoint to lookup objects by name and get their IDs. Here are the IDs for some of the most used objects:

| Code point | Object |
|---|---|
| P0 | Sun |
| P1 | Moon |
| P2 | Mercury |
| P3 | Venus |
| P4 | Mars |
| P5 | Jupiter |
| P6 | Saturn |
| P7 | Uranus |
| P8 | Neptune |
| P9 | Pluto |
| A2060 | Chiron |
| P10 | Mean Ascending Node |
| P11 | True Ascending Node |
| P23 | Mean Descending Node |
| P24 | True Descending Node |
| P14 | Earth |
| P12 | Mean Lilith |
| P13 | True Lilith |
| P21 | Natural Lilith |
| A1 | Ceres |
| A2 | Pallas |
| A3 | Juno |
| A4 | Vesta |
| H0 | Cupido |
| H1 | Hades |
| H2 | Kronos |
| H3 | Apollon |
| H4 | Admetos |
| H5 | Vulkanus |
| H6 | Poseidon |
| L118 | Part of Fortune |
| L119 | Part of Spirit |
| S3071 | Aldebaran |
| S1351 | Regulus |
| S3099 | Sirius |
| S1224 | Vega |
| S2665 | Spica |

<br>

### Simbad Integration

When working with stars and stellar objects, If our database does not contain the object you're looking for, it is possible to retrieve it directly from the simbad database using the following format:

| Example | Descripton |
|---|---|
|QS:HD 25452| Get Object HD 25452 (Star)|
|QS:NGC 3726| Get Object NGC 3726 (Galaxy)|

<br><br><br>
