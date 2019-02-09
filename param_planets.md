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
	.sidebar {
		width: 30%
	}
	.navigation li {
		padding: 5px;
	}
</style>

<script>
	window.onload = function(){
		if (location.hash) {
			let target = location.hash;
			document.querySelector(".content").scroll({top:document.querySelector(target).offsetTop,behavior:"smooth"})
		}
	}
</script>

<br>

## Parameters - Planets

An array of code points specifying the objects that should be calculated. The code point format should be a type identifier followed by a number.

| Example | Descripton |
|---|---|
|`P0`|Planet number 0 (sun)|
|`S156`|Star number 156 (regulus)|
|`A3`|Asteroid number 3 (juno)|

<br>

### Parameters - Planets - Object Type

| Object Type | Descripton |
|---|---|
| P | Planets and specific objects |
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
| DL | Arabic parts/lots (no reverse) |
| NL | Arabic parts/lots (force reverse) |

<br>

### Parameters - Planets - Code Points

Asteroids's code points follow the same numbering as their official designation. Other code points do not follow any specific numbering system, but you can use the [Search](/astrologico/search.html) endpoint to lookup objects by name and get their code points. Here are the code points for some of the most used objects:

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
| S186 | Aldebaran |
| S156 | Regulus |
| S120 | Sirius |
| S161 | Vega |
| S195 | Spica |

<br><br><br>
