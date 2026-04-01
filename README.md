# Currency Converter

A lightweight, browser-based currency converter that fetches live exchange rates and displays country flags for selected currencies.

---

## Overview

This project is a frontend-only web application that allows users to convert between world currencies in real time. It queries a public exchange rate API and dynamically updates the conversion result without any page reloads.

---



## Features

- Convert between 150+ world currencies
- Live exchange rates fetched from the ExchangeRate API
- Country flags displayed alongside currency selectors
- Swap button to quickly reverse the conversion direction
- Defaults to USD to INR on page load
- Input validation with fallback to 1 for empty or invalid amounts

---

## Technologies Used

- HTML5
- CSS3
- Vanilla JavaScript (ES6+)
- Font Awesome 6 (icons via CDN)
- Google Fonts - Poppins (via CDN)
- ExchangeRate API (https://api.exchangerate-api.com)
- FlagsAPI (https://flagsapi.com)

---

## Getting Started

No build tools, package managers, or server setup is required. The project runs entirely in the browser.

### Steps

1. Clone or download the repository.
2. Open `index.html` in any modern web browser.
3. The app will automatically load and fetch the current USD to INR exchange rate.

```bash
git clone https://github.com/AnasMumtaz2004/Currency-Converter.git
cd currency-converter
open index.html
```

---

## How It Works

1. On page load, `app.js` populates both currency dropdowns using the `countryList` object from `codes.js`.
2. When the user clicks "Get Exchange Rate", the app fetches the latest rates from:
   ```
   https://api.exchangerate-api.com/v4/latest/{FROM_CURRENCY}
   ```
3. The conversion result is calculated and displayed in the message box.
4. Flags update automatically when the selected currency changes, using the FlagsAPI service.
5. The swap icon reverses both selected currencies and re-fetches the rate.

---

## API Reference

### ExchangeRate API

- Base URL: `https://api.exchangerate-api.com/v4/latest`
- Usage: `GET /v4/latest/{currency_code}`
- Response includes a `rates` object with conversion values for all supported currencies.
- Free tier is available with rate limits.

### FlagsAPI

- Base URL: `https://flagsapi.com`
- Usage: `https://flagsapi.com/{COUNTRY_CODE}/flat/64.png`
- Returns a 64x64 flat-style flag image for the given ISO 3166-1 alpha-2 country code.

---

## Known Limitations

- Relies on a free public API which may have rate limits or occasional downtime.
- No offline support or caching of previous results.
- Some currency codes (e.g., ANG, AQD) may not have available flags.

---

## License

This project is open source and available under the MIT License.
