# Actor - Google Flights Scraper

When it comes to accessing data from Google Flights easily, our solution is the key. Our Google Flights data scraper offers a range of features to make your data retrieval seamless:

- Complete Round Trip Scraping: Get all the details you need, including departure and return dates, in one go.
- Effortless One-Way Trip Scraping: Simply provide the departure date, and our scraper will fetch the necessary information.
- Flexible People Options: Whether you're searching for flights for adults, teens, children, or infants, our scraper can handle it all.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex-support/google-flights-scraper/issues).

## Input Parameters

The input of this scraper should be JSON-containing. Possible fields are:

- `startUrls`: (Optional) (Array) Start URLs for the actor to initiate the search.

- `mode`: (Optional) (String) Mode for the actor. It can be either `roundTrip` for Round trip or `oneWay` for One-way trips.

- `departure`: (Optional) (String) 3-letter destination airport code. Ex: VIE.

- `arrival`: (Optional) (String) 3-letter arrival airport code. Ex: AMS.

- `departureDate`: (Optional) (String) Date for departure. Should be in the format of `YYYY-MM-DD`. Ex: 2024-02-21.

- `returnDate`: (Optional) (String) Date for return. It is required for Round trips. Should be in the format of `YYYY-MM-DD`. Ex: 2026-02-21.

- `currency`: (Optional) (String) 3-letter currency symbol string. Ex: USD

- `adults`: (Optional) (Number) Number of adults that will be included on the flight. The minimum number is 1.

- `children`: (Optional) (Number) Number of children (2-11 years old) that will be included on the flight.

- `infantsOnSeat`: (Optional) (Number) Infants on seat (Under 2 years old) that will be included on the flight.

- `infantsOnLap`: (Optional) (Number) Infants on lap (Under 2 years old) that will be included on the flight.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use <a href="https://www.apify.com/docs/proxy">Apify Proxy</a>.

### Compute Unit Consumption

The actor is optimized to run in a very fast manner and scrape the flights in the most performant way. Therefore, it forefronts all flight result requests. If the actor doesn't block very often it'll scrape 100 flights in 30 seconds with ~0.01-0.05 compute units.

### Google Flights Scraper Input example

```json
{
    "startUrls": [
        "https://www.google.com/travel/flights/search?tfs=CBwQAhoeEgoyMDI0LTA3LTAyagcIARIDQU1TcgcIARIDQkVSGh4SCjIwMjQtMDctMzFqBwgBEgNCRVJyBwgBEgNBTVNAAUgBcAGCAQsI____________AZgBAQ"
    ],
    "mode": "oneWay",
    "departure": "LHR",
    "arrival": "MAD",
    "departureDate": "2024-07-01",
    "returnDate": "2024-08-01",
    "adults":1,
    "proxy":{
        "useApifyProxy": true
    }
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on.
When items are loaded from the page, you should see a message about this event with a loaded item count.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## Google Flights Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Google Flights actor.

## Scraped Google Flights Flights

The structure of each item in Google Flights looks like this:

```json
{
	"departureTime": "4:35 PM",
	"arrivalTime": "7:55 PM",
	"price": "$305",
	"totalDuration": "2 hr 20 min",
	"from": "LHR",
	"to": "MAD",
	"airline": "Iberia",
	"stops": "Nonstop",
	"flightNumber": "BA 464"
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
