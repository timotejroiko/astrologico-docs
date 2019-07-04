---
layout: page
title: Parameters - Derived
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

<script>
	window.onload = function(){
		if (location.hash) {
			let target = location.hash;
			document.querySelector(".content").scroll({top:document.querySelector(target).offsetTop,behavior:"smooth"})
		}
	}
</script>

<br>

## Derived

An indexed array to create a derived chart from the [Date](/astrologico/param_date.html) parameter.

| Index | Type | Descripton |
|---|---|---|
| 0 | string | Derived chart type |
| 1 | number/string | Derived chart option |

Currently derived chart supports the following types in index 0:

| Type | Description |
|---|---|
| [persona](#persona) | Create a "Persona" chart |
| [hds](#hds) | Create a "Design" chart for the Human Design System |

<br>

### Derived - Persona
{:id="persona"}

A "Persona" chart is the first time the sun transits over a person's natal planet. When using a Persona chart, the second index should contain the desired Object ID.

| Index | Type | Descripton |
|---|---|---|
| 0 | string | "persona" |
| 1 | string | Object ID |

<br>

### Derived - HDS
{:id="hds"}

A "Design" chart is a prenatal or a postnatal chart used in the Human Design System. When using a Design chart, the second index should contain the Design type.

| Index | Type | Descripton |
|---|---|---|
| 0 | string | "hds" |
| 1 | integer | Design type |

The following Design types are supported:

| Design Type | Descripton |
|---|---|
| 1 | Prenatal Solar Design (Default) |
| 2 | Prenatal Lunar Design |
| 3 | Prenatal Solar Minute Design |
| 4 | Prenatal Lunar Minute Design |
| 5 | Postnatal Solar Design |
| 6 | Postnatal Lunar Design |
| 7 | Postnatal Solar Minute Design |
| 8 | Postnatal Lunar Minute Design |

<br>

### Examples

|GET|POST|Description|
|---|---|---|
|`derived=persona|P2`|`derived:["persona","P2"]`| Mercury Persona chart |
|`derived=hds|1`|`derived:["hds",1]`| Default "Design" chart for the Human Design System |

<br><br><br>