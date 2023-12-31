# SkySavvy Chrome Extension

<img src="img/screenshot.png" alt="SkySavvy screenshot" />

## Install

[Install via the Chrome Web Store](https://chrome.google.com/webstore/detail/skysavvy-enhance-google-f/kpdeplhmnofpohflebkiigblcpogmdeg)

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

* Adds seat and leg room information to each flight
* Adds a FlightAware link for each flight segment
* Adds detailed aircraft IATA code and Wikipedia link
* Adds SeatGuru link for the specific aircraft type
* Adds LoungeBuddy links for lounges in the origin and destination airports
* Adds airline miles award program data
* Adds estimated award program point values
* Adds airline transfer partner data (and point transfer ratios)
* Adds visual call outs for Delta One, Delta One Suites, and Qsuites in business class

| Before | After |
|--------|-------|
| <img src="img/flight-before.png" />   | <img src="img/flight-after.png" alt="SkySavvy screenshot" />  |
| <img src="img/details-before.png" />   | <img src="img/details-after.png" alt="SkySavvy screenshot" />  |
| <img src="img/aircraft-before.png" />   | <img src="img/aircraft-after.png" alt="SkySavvy screenshot" />  |
| <img src="img/biz-before.png" />   | <img src="img/biz-after.png" alt="SkySavvy screenshot" />  |

### Additional Filters

* Adds a filter to show only lie-flat business class seats
* Adds a filter to show only business class suites (Delta One, Qsuites, etc.)

| Before | After |
|--------|-------|
| <img src="img/filters-before.png" />   | <img src="img/filters-after.png" alt="SkySavvy screenshot" />  |

### Flight Media
For each supported flight search result, SkySavvy injects photos, videos, and links to relevant flight review blogs, or walkthrough videos. This is useful when flying business class if you want to find out what the seat type and cabin arrangement looks like.

* Adds relevant media of aircraft, cabins, seats, etc.

| Before | After |
|--------|-------|
| <img src="img/media-before.png" />   | <img src="img/media-after.png" alt="SkySavvy screenshot" />  |
| <img src="img/video-before.png" />   | <img src="img/video-after.png" alt="SkySavvy screenshot" />  |

### Lightweight and Ad/Tracker-Free
SkySavvy takes your privacy seriously (see [Security and Privacy](#security-and-privacy) below). The SkySavvy extension is designed to work with minimal dependencies, run only on the Google Flights page (no other domains), and does not include any ads, trackers, or other third-party scripts. The entire extension is < 500kb in size.

## Options

SkySavvy supports configuring what page modifications are made. Currently, this includes:

* Enabling/disabling the extension entirely
* Enabling/disabling the display of inline media (photos, videos, etc.)
* Enabling/disabling the display of FlightAware links
* Enabling/disabling the display of award program and transfer partner data

These options can be configured by clicking on the extension and checking or unchecking the boxes:

<img src="img/options.png" width="400px" />

## Security and Privacy

The SkySavvy extension uses Chrome manifest v3 and injects its background script into only pages matching the format `https://www.google.com/travel/flights*`. It requests only the `storage` permission, used to persistently save the configuration options for the extension.

SkySavvy does not collect, transmit, or store any user data, private data, search data, or otherwise. All data is processed locally within the extension. SkySavvy does not include any trackers, ads, or other third-party scripts other than Jquery (loaded locally).

A complete copy of the `manifest.json` file can be seen below:

<details>

```json
{
    "manifest_version": 3,
    "name": "SkySavvy - Enhance Google Flights",
    "description": "Enhanced Google Flights for savvy travelers",
    "version": "1.4.0",
    "version_name": "1.4.0 - Beta",
    "icons": {
        "16": "images/icon-16.png",
        "32": "images/icon-32.png",
        "48": "images/icon-48.png",
        "128": "images/icon-128.png"
    },
    "content_scripts": [
        {
            "matches": [
                "https://www.google.com/travel/flights*",
                "https://www.google.ca/travel/flights*",
                "https://www.google.com.pr/travel/flights*",
                "https://www.google.ie/travel/flights*",
                "https://www.google.ch/travel/flights*",
                "https://www.google.com.my/travel/flights*",
                "https://www.google.be/travel/flights*",
                "https://www.google.nl/travel/flights*",
                "https://www.google.pt/travel/flights*",
                "https://www.google.es/travel/flights*",
                "https://www.google.de/travel/flights*",
                "https://www.google.com.br/travel/flights*",
                "https://www.google.co.nz/travel/flights*",
                "https://www.google.co.uk/travel/flights*",
                "https://www.google.at/travel/flights*",
                "https://www.google.fr/travel/flights*",
                "https://www.google.com.au/travel/flights*",
                "https://www.google.no/travel/flights*",
                "https://www.google.se/travel/flights*",
                "https://www.google.dk/travel/flights*",
                "https://www.google.it/travel/flights*",
                "https://www.google.com.mx/travel/flights*",
                "https://www.google.co.in/travel/flights*",
                "https://www.google.pl/travel/flights*",
                "https://www.google.co.id/travel/flights*",
                "https://www.google.co.jp/travel/flights*",
                "https://www.google.ru/travel/flights*"
            ],
            "js": [
                "jquery.min.js",
                "flights.js"
            ],
            "css": [
                "styles.css"
            ]
        }
    ],
    "web_accessible_resources": [
        {
            "matches": [
                "https://www.google.com/*",
                "https://www.google.ca/*",
                "https://www.google.com.pr/*",
                "https://www.google.ie/*",
                "https://www.google.ch/*",
                "https://www.google.com.my/*",
                "https://www.google.be/*",
                "https://www.google.nl/*",
                "https://www.google.pt/*",
                "https://www.google.es/*",
                "https://www.google.de/*",
                "https://www.google.com.br/*",
                "https://www.google.co.nz/*",
                "https://www.google.co.uk/*",
                "https://www.google.at/*",
                "https://www.google.fr/*",
                "https://www.google.com.au/*",
                "https://www.google.no/*",
                "https://www.google.se/*",
                "https://www.google.dk/*",
                "https://www.google.it/*",
                "https://www.google.com.mx/*",
                "https://www.google.co.in/*",
                "https://www.google.pl/*",
                "https://www.google.co.id/*",
                "https://www.google.co.jp/*",
                "https://www.google.ru/*"
            ],
            "resources": [
                "data/*.json",
                "images/*",
                "interceptor.js"
            ]
        }
    ],
    "action": {
        "default_title": "SkySavvy",
        "default_icon": {
            "16": "images/icon-16.png",
            "32": "images/icon-32.png",
            "48": "images/icon-48.png",
            "128": "images/icon-128.png"
        },
        "default_popup": "popup/popup.html"
    },
    "permissions": [
        "storage"
    ]
}
```

</details>

## FAQ

#### Why should I use SkySavvy?
SkySavvy enhances Google Flights for experienced travelers by improving the interface and adding information, links, photos, and videos to the flight search results.

#### How do I install SkySavvy?
SkySavvy is installed via the Chrome Web Store by clicking "install." No other steps or sign up are required.

#### Does SkySavvy have its own website?
Not at this time. The only way to use SkySavvy is via the Chrome extension.

#### Is SkySavvy safe to use?
Yes. The SkySavvy extension only runs on the Google Flights webpage and does not depend on any third-party code. SkySavvy does not have any trackers or ads.

#### Why does Chrome say the extension needs access to google.com?
The Chrome Extension permissions model is limited to displaying the top-level domain in the "accept permissions" dialog. However, SkySavvy only runs on `https://www.google.com/travel/flights*`. SkySavvy does not have access to any other Google sites.

#### SkySavvy is showing inaccurate data.
Please report the issue (see [Support](#support) below). Unfortunately, with 10s of 1000s of combinations of airlines, aircraft, airports, and routes, we sometimes have inaccurate data. But we'll do our best to fix it!

## Known Issues
SkySavvy is under active development. We're aware of several issues that may affect your experience using SkySavvy:

* Injected flight data for a search result disappears if you expand another search result. You can get it back by collapsing and expanding the same flight again.
* Injected flight data is not shown on the final flight summary confirmation page
* Injected seat and legroom information may flash or disappear when flight details are expanded and collapsed
* Some FlightAware links do not match the routes shown by Google Flights. We believe this is due to airlines changing routes > 30 days in the future.
* Some aircraft data may be inaccurate if Google doesn't specify the specific aircraft model. For example: Boeing 767 could be a Boeing 767-300 or 767-400.

## Support
Please use GitHub to file [bug reports](https://github.com/matthewdfuller/skysavvy-docs/issues/new?assignees=&labels=&projects=&template=bug_report.md&title=%5BBUG%5D) or [feature requests](https://github.com/matthewdfuller/skysavvy-docs/issues/new?assignees=&labels=&projects=&template=feature_request.md&title=).

## Roadmap
I have a number of things planned for the next version of SkySavvy. A few sneak peaks:

* Adding additional search filters for things like points transfer partners
* More customized information about business class flights (e.g., which seats are the bes)
* Seat maps from [Aerolopa](https://www.aerolopa.com/)
* Support for more airlines, flights, and aircraft
* Flight review data from popular travel sites
* And more!

## Buy Me a Coffee

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/matthewdfuller)

If you've found SkySavvy useful, please consider buying me a coffee to help support server costs.
