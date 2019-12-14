## Planets

The planets field contains all the calculated planetary data keyed by Object IDs.

| Value | Type | Descripton |
|---|---|---|
| [Object ID](response_data.md) | Object | Object containing planetary data for the specified object |
| [Object ID](response_data.md) | Object | Object containing planetary data for the specified object |
| ... | Object | etc... |

For example, the ID for the Sun is `P0`, the response for the sun data will be:

```json
{
	"planets": {
		"P0": {
			//planetary data for the Sun
		}
	}
}
```

<br>