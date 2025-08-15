# PyQt Weather App

A simple desktop GUI application that allows you to enter a city name and fetch current weather information from OpenWeatherMap. 
The app displays temperature in Fahrenheit, weather emojis, and descriptive weather conditions with clear error handling for network issues.

## Features

- Clean, intuitive GUI built with PyQt5
- Real-time weather data from OpenWeatherMap API
- Temperature display in Fahrenheit
- Weather condition emojis for visual feedback
- Descriptive weather text
- Comprehensive error handling for HTTP and network issues
- Secure API key management using environment variables

## Technology Stack

- **Python 3.x** - Core programming language
- **PyQt5** - GUI framework
- **requests** - HTTP library for API calls
- **python-dotenv** - Environment variable management
- **OpenWeatherMap Current Weather Data API** - Weather data source

## Prerequisites

- Python 3.x installed on your system
- OpenWeatherMap API key (free registration at [openweathermap.org](https://openweathermap.org/api))

## Installation & Setup

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

### 2. Create and Activate Virtual Environment

**macOS/Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows (PowerShell):**
```bash
py -m venv .venv
.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
pip install PyQt5 requests python-dotenv
```

Alternatively, if you have a `requirements.txt` file:
```bash
pip install -r requirements.txt
```

### 4. Configure API Key

Create a `.env` file in the project root directory:

```ini
OPENWEATHER_API_KEY=your_api_key_here
```

**Important:** Never commit your actual API key to version control. The `.env` file should be added to your `.gitignore`.

### 5. Run the Application

```bash
python main.py
```

## Project Structure

```
PyQt-Weather-App/
├── main.py              # Main application file
├── .env                 # API key configuration (create this)
├── .env.example         # Example environment file (optional)
├── requirements.txt     # Python dependencies (optional)
├── .gitignore          # Git ignore file (recommended)
└── README.md           # This file
```

## Application Architecture

The application is structured as a single-file desktop GUI with the following key components:

- **WeatherApp** - Main QWidget class containing the UI elements (labels, input field, button)
- **get_weather()** - Handles API requests and error management
- **display_weather()** - Renders temperature, emoji, and weather description
- **get_weather_emoji()** - Static method that maps OpenWeatherMap weather codes to appropriate emojis

## API Information

The app makes requests to:
```
https://api.openweathermap.org/data/2.5/weather?q=<CITY>&appid=<API_KEY>
```

Temperature conversion from Kelvin to Fahrenheit is handled in the application code. For direct Fahrenheit responses, 
you can modify the API call to include `&units=imperial`.

## Optional Files

### requirements.txt
```
PyQt5
requests
python-dotenv
```

### .env.example
```
OPENWEATHER_API_KEY=
```

## Known Issues

- **macOS users:** You may see a Qt message about the Calibri font. This is safe to ignore, or you can modify the
- stylesheet to use a different font family.

## Error Handling

The application includes comprehensive error handling for:
- Network connectivity issues
- Invalid city names
- API rate limiting
- Missing or invalid API keys
- HTTP request failures

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
