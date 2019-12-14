## Language

Sets the language to localize certain functions using a 2-digit language code.

| Type | Descripton |
|---|---|
| String | language code in `ISO 639-1` format |

The following functions and values can be localized:

| Field | Kind | Descripton |
|---|---|---|
| [querylocation](parameters_location.md#querylocation) | Parameter | Localized search \* |
| [queryResult](response_metadata.md#location) | Response | Localized result |
| [name](response_metadata.md#tz) | Response | Localized Timezone name |

\* A localized querylocation request allows for language-specific searches, for example searching for `rome` in English will return `Rome, Italy` but searching for `rome` in Italian will return `Rome, Georgia, Stati Uniti d'America` (Rome, Georgia, United States).

<br>

### Examples

Set language to Italian, allowing for location searches using Italian terms and names as well as returning location and timezone results in Italian.

| GET | POST | Descripton |
|---|---|---|
| `language=it` | `language:"it"` | Set language to Italian |

<br>