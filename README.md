# Yak Collective IT infrastructure map

Prototype documentation tool for [Yak Collective](https://yakcollective.org) [IT Infrastructure](https://roamresearch.com/#/app/ArtOfGig/page/6fhTlx1p_).

## Symbol key

| Symbol              | Macro              | Meaning                                                                                |
|:-------------------:|:------------------:|:-------------------------------------------------------------------------------------- |
| Double Green Circle | `STATIC_DATA`      | Website or service that functions as a (relatively) static data source/destination     |
| Green Oval          | `EXTERNAL_SERVICE` | Externally-facing web service used by YC members/participants (and sometimes others)   |
| Blue Oval           | `INTERNAL_SERVICE` | Internally-facing web service used by few YC members (sometimes not accessible at all) |
| Blue Rectangle      | `APPLET`           | A function, service applet, or internal tool; contained by and run by some service     |
| Red Line            | `USER_DATA`        | Manual data flow (someone creates an account, reviews a list and takes action, etc.)   |
| Black Line          | `AUTO_DATA`        | Automatic data flows (service takes action based on a timer, webhook, etc.)            |

## Development

Most (all?) browsers restrict how JavaScript can access `file://` URLs, even for HTML files opened directly from the file system. For this reason, you'll need to fire up a local web server to work on `index.html`, etc. Python 3 makes this easy:

```bash
python3 -m http.server 8080
```

Then go to <https://localhost:8080/index.html> to view the infrastrucutre diagram. Reload after making any changes.

## Build

To generate an SVG for Roam, use:

```bash
sed -E -f macros.sed infrastructure.dot | dot -Tsvg > infrastructure.svg
```
