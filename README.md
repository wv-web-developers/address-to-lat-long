# address-to-lat-long

A simple tool that turns a street address into latitude and longitude. It is a single HTML page: no install, no account, no API key.

## Features

- **Single lookup**: type an address and get the latitude, the longitude and the combined pair, each with a Copy button.
- **Batch mode**: paste a list of addresses (one per line) or load a `.csv` or `.txt` file, then download the results as a CSV.
- **Matched address shown**: every result includes the full address the service matched, so you can confirm it found the right place.
- **Retry failed**: addresses that are not found are flagged and stay editable, so you can fix them and retry only those.

## How to run

1. Download `index.html` (or clone this repo).
2. Double-click `index.html` to open it in your browser.

That's all. An internet connection is required, because lookups are sent to the OpenStreetMap Nominatim service.

## How to use

### Single lookup

Type an address in the box at the top and press **Look up**.

### Batch mode

1. Paste addresses one per line, or choose a file:
   - `.txt`: one address per line.
   - `.csv`: the column whose header contains "address" is used. If there is no such column, each row's columns are joined into one address.
2. Check the list in the text box, then press **Start batch**.
3. Fix any rows marked "Not found" and press **Retry failed**.
4. Press **Download CSV** to save `geocoded.csv` with these columns: `address`, `matched_address`, `latitude`, `longitude`, `status`.

Excel `.xlsx` files are not supported directly. Save the sheet as CSV first.

## Good to know

- **Speed**: batch lookups run at about one address per second, the limit set by the free service. 500 addresses take roughly 9 minutes.
- **Volume**: the free service is meant for occasional use. It suits lists of a few hundred to a few thousand addresses, not regular bulk jobs.
- **Check the matches**: a wrong match still shows as "Found". For example, "350 Fifth Ave, New York, NY" can match a 5th Avenue elsewhere in New York State. Adding a ZIP code usually fixes this.
- **Privacy**: the addresses you look up are sent to `nominatim.openstreetmap.org`. Nothing else leaves your computer.

## Credits

Geocoding by [OpenStreetMap Nominatim](https://nominatim.openstreetmap.org/). Data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright), available under the Open Database License.
