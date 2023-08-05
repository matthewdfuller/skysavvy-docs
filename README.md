# SkySavvy Chrome Extension

<img src="img/screenshot.png" alt="SkySavvy screenshot" />

## Install

(Link to Chrome Web Store)

## Background

SkySavvy is a Chrome extension that enhances Google Flights with style changes and additional data in flight search results. As a heavy user of Google Flights, I often found myself searching for flight reviews, more detailed aircraft data, and miles and award transfer information. SkySavvy is my approach to bringing that data directly into the Google Flights UI.

## Features

### Basic Page Style Enhancements
SkySavvy makes several changes to the Google Flights interface:

* Widens the page to reduce clutter and take advantage of widescreen monitors
* Hides the footer that contained unnecessary links
* Hides various annoying disclaimers that cluttered the interface (e.g., "Displayed currencies may differ", "Prices include fees", etc.)
* Hides CO2 emissions data from the top-level of each search result (the same information is still available in the expanded view)
* Supports both light and dark mode

| Before | After |
|--------|-------|
| <img src="img/style-before.png" />   | <img src="img/style-after.png" alt="SkySavvy screenshot" />  |

### Holiday Highlighting

* SkySavvy highlights holidays (US only for now) in the date-pickers, helping you easily visualize travel dates that may be more expensive.

| Before | After |
|--------|-------|
| <img src="img/holiday-before.png" />   | <img src="img/holiday-after.png" alt="SkySavvy screenshot" />  |

### Additional Flight Data
For each supported flight search result, SkySavvy injects additional data about the airports, airline, aircraft, flight, seats, and award programs.

* Adds a FlightAware link for each flight segment
* Adds detailed aircraft IATA code and Wikipedia link
* Adds SeatGuru link for the specific aircraft type
* Adds LoungeBuddy links for lounges in the origin and destination airports
* Adds airline miles award program data
* Adds airline transfer partner data (and point transfer ratios)
* Adds visual call outs for Delta One, Delta One Suites, and Qsuites in business class

| Before | After |
|--------|-------|
| <img src="img/flight-before.png" />   | <img src="img/flight-after.png" alt="SkySavvy screenshot" />  |
| <img src="img/details-before.png" />   | <img src="img/details-after.png" alt="SkySavvy screenshot" />  |
| <img src="img/aircraft-before.png" />   | <img src="img/aircraft-after.png" alt="SkySavvy screenshot" />  |

### Flight Media
For each supported flight search result, SkySavvy injects photos, videos, and links to relevant flight review blogs, or walkthrough videos. This is useful when flying business class if you want to find out what the seat type and cabin arrangement looks like.


## Options

## Security and Privacy

## FAQ

## Known Issues
* Disappears when a new row is expanded
* Doesn't show on the final confirmation page
* Only have holidays for 2023
* Some FlightAware links don't match
* Some aircraft data may be inaccurate if Google doesn't specific (ex: 737-4 vs 3)


## Support

## Roadmap

## Buy Me a Coffee