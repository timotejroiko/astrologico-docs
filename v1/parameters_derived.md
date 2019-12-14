## Derived

An indexed array to create a derived chart from the [Date](parameters_date.md) parameter. Derived charts increase the request's total cost by 1.

| Index | Type | Descripton |
|---|---|---|
| 0 | String | Derived chart type ("persona", "hds") |
| 1 | Integer/String | Derived chart option |

Currently derived charts supports the following types at index 0:

| Type | Description |
|---|---|
| [persona](#persona) | Create a "Persona" chart |
| [hds](#hds) | Create a "Design" chart for the Human Design System |

<br>

### Derived - Persona

A "Persona" chart is the moment the sun transits over a person's natal planet for the first time. When using a Persona chart, the second index should contain the Object ID of the desired planet or object.

| Index | Type | Descripton |
|---|---|---|
| 0 | String | "persona" |
| 1 | String | Object ID |

<br>

### Derived - HDS

A "Design" chart is a prenatal or a postnatal chart used in the Human Design System. When using a Design chart, the second index should contain the Design type ID as shown below.

| Index | Type | Descripton |
|---|---|---|
| 0 | String | "hds" |
| 1 | Integer | Design type ID |

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
|derived=persona\|P2|derived:["persona","P2"]| Mercury Persona chart |
|derived=hds\|1|derived:["hds",1]| Default "Design" chart for the Human Design System |

<br>