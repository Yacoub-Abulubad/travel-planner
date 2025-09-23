# travel-planner

## What this does

This is a neat service that could take a couple of input fields and provide you with nice options as a travel plan. 

Some inputs may be:

- `budget`
- `current location`
- `type of destination`
- `desired weather`
- `passport(s)`
- `etc`

And should output something like this:

```python
{
    "flights":[
        "flight A",
        "flight B",
        "flight C",
    ],
    "hotels":[
        "hotel A",
        "hotel B",
        "hotel C",
    ]
}
```

The output should be ranked by best match in terms of the given inputs. Additionally there can be an AI recommendation model implemented.