# Weather Web App

A simple browser-based weather application built with vanilla HTML, CSS, and JavaScript. Enter any city name to view its current weather conditions along with a short-term hourly forecast.

## Features

- **City search** — enter any city name and fetch its live weather data.
- **Current conditions** — displays the current weather for the searched city.
- **Hourly forecast** — shows the next 24 hours of forecasted weather in 3-hour intervals, including time, weather icon, and temperature (in °C).
- **Error handling** — alerts the user if no city is entered, or if the weather data request fails.
- **Clean, glassmorphism-style UI** — a frosted-glass card layout with a soft purple background, blurred backdrop, and rounded corners.

## Tech Stack

- **HTML5** — page structure (`weather_app.html`)
- **CSS3** — styling, including `backdrop-filter` blur effects and flex-based layout (`weather_app.css`)
- **JavaScript (Vanilla, ES6)** — API calls and DOM manipulation (`weather_app.js`)
- **[OpenWeatherMap API](https://openweathermap.org/api)** — current weather and 5-day/3-hour forecast data

## File Structure

```
weather-web-application/
├── weather_app.html      # Main HTML structure
├── weather_app.css       # Styling for the weather card and hourly forecast
├── weather_app.js        # Weather-fetching logic and DOM rendering
└── README.md
```

## Getting Started

### Prerequisites

You'll need a free API key from [OpenWeatherMap](https://openweathermap.org/api):

1. Create an account at [openweathermap.org](https://home.openweathermap.org/users/sign_up).
2. Generate an API key from your account dashboard.
3. Open `weather_app.js` and replace the placeholder on line 2:

   ```js
   const apiKey = 'YOUR-API-KEY-HERE';
   ```

   with your actual key.

> **Note:** Newly generated OpenWeatherMap API keys can take up to a couple of hours to activate.

### Running the app

No build tools or installation required:

1. Clone or download this repository.
2. Open `weather_app.html` directly in your browser (double-click, or right-click → "Open with" your browser of choice).
3. Enter a city name and click **Search**.

## How It Works

1. The user types a city name into the input field and clicks **Search**, which triggers `getWeather()`.
2. The app calls two OpenWeatherMap endpoints in parallel:
   - `/data/2.5/weather` — current conditions for the city.
   - `/data/2.5/forecast` — a 5-day forecast in 3-hour steps.
3. The forecast response is sliced to the next 8 entries (24 hours) and rendered into the `#hourly-forecast` container via `displayHourlyForecast()`, showing the hour, weather icon, and temperature for each interval.
4. If the city field is empty or a request fails, the app shows an alert rather than failing silently.

## Possible Improvements

- Move the API key out of client-side JS (it's currently visible to anyone viewing the page source) — typically done via a small backend proxy for production apps.
- Add a loading state while data is being fetched.
- Support switching between °C and °F.
- Add a 7-day forecast view alongside the existing hourly breakdown.

## Author

**Yash Raj Sahu**
[GitHub](https://github.com/Yash00109) · [LinkedIn](https://linkedin.com/in/yash-raj-sahu-698a64273)
