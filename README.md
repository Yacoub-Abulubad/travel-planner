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

## Back end

Flight searcher (whatever api)

Hotel/apartment finder (Booking.com api)

Weather app or forecasting to look for the best weather

Visa indexing according to passport (static DB)

### Orchestration

Get input from user (a single person object), query countries with specified visa status according to passport.

Find countries from that list which would have the categories of travel type within the date range.

Search flights from user's country to countries in that list. If flight price exceedes the rule below, exclude the flight

```
Short trip (1–7 days, domestic/regional)	40–60%
Mid-length (1–2 weeks, international)	25–40%
Long-term travel (1+ month)	10–25%
```

If no flights to country left available, remove country from list.

Search for accomodation based on users preference.

```
flight cost + accomodation <= budget 
```

Rank best destination based on price, match rate with travel type, distance and desired weather.