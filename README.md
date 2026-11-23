# Weather App

A simple, responsive weather application built with HTML, CSS, and JavaScript. It uses the OpenWeatherMap Current Weather API to retrieve live weather information for a city entered by the user.

## Features

- Search for current weather by city name.
- Display the city name and temperature in Celsius.
- Display humidity and wind speed.
- Show a weather icon based on the reported conditions.
- Display an error message when the city cannot be found.
- Responsive card-style interface with a gradient background.

## Technologies Used

- HTML5
- CSS3
- JavaScript (Fetch API and async/await)
- [OpenWeatherMap Current Weather API](https://openweathermap.org/current)

## Project Structure

```text
weather_app/
├── images/
│   ├── clear.png
│   ├── clouds.png
│   ├── drizzle.png
│   ├── humidity.png
│   ├── mist.png
│   ├── rain.png
│   ├── search.png
│   ├── snow.png
│   └── wind.png
├── index.html
├── script.js
└── style.css
```

The current application JavaScript is written inside a `<script>` element in `index.html`. The `script.js` file is currently empty and is not linked by the HTML page.

## Getting Started

### 1. Download or clone the project

If you have cloned the repository:

```bash
git clone <your-repository-url>
cd weather_app
```

Alternatively, extract the project ZIP file.

### 2. Configure the API key

The application uses an OpenWeatherMap API key. In `index.html`, locate:

```javascript
const apiKey = "YOUR_API_KEY";
```

Replace `YOUR_API_KEY` with your own API key from [OpenWeatherMap](https://home.openweathermap.org/api).

> **Important:** The current project places the API key in browser-side JavaScript. Anyone inspecting the page can see it. For a public deployment, do not expose a private API key in frontend code; use a backend endpoint or another secure proxy to make API requests.

### 3. Run the application

Open `index.html` in a web browser. You can also use the Live Server extension in Visual Studio Code:

1. Open the project folder in VS Code.
2. Install the **Live Server** extension if it is not already installed.
3. Right-click `index.html`.
4. Select **Open with Live Server**.

No package installation or build process is required for the current version.

## How to Use

1. Open the application in your browser.
2. Enter a city name in the search field.
3. Click the search button.
4. The application requests the city's current weather from OpenWeatherMap.
5. The weather card displays the temperature, humidity, wind speed, and a matching weather icon.

If the city is not found, an **Invalid City Name** message is displayed.

## API Endpoint

The application requests data from the OpenWeatherMap Current Weather endpoint using metric units:

```text
https://api.openweathermap.org/data/2.5/weather?units=metric&q={city}&appid={API_KEY}
```

## Current Limitations

- Weather information is searched by city name only.
- The current code handles a not-found response (HTTP 404), but does not yet show friendly messages for network errors or other API failures.
- The search is triggered by clicking the button; pressing Enter is not currently implemented.
- The displayed wind speed is labelled as `km/hr`, although the API's standard wind-speed value is in metres per second unless converted. The displayed value may therefore need a conversion or a corrected unit label.
- The `script.js` file is empty; the JavaScript currently lives in `index.html`.

## Possible Improvements

- Move JavaScript into `script.js` and load it with a script reference.
- Add Enter-key search support.
- Add loading and network-error states.
- Convert wind speed to km/h or display the API's actual unit.
- Add support for more weather conditions, including snow.
- Add a default city or location-based weather.
- Move API requests behind a backend to protect the API key.

## License

No license is specified for this project. Add a license file if you intend to publish or distribute it.
