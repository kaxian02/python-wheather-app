🌤️ Python Weather App

A simple Python Weather Application that fetches real-time weather information for any city using the OpenWeatherMap API.
This project demonstrates how to work with APIs and handle JSON data in Python.

🚀 Features

Fetches live weather data for any city

Displays:

Temperature (°C)

Humidity (%)

Wind speed (m/s)

Weather description (e.g., clear sky, rain)

Handles invalid city names gracefully

Console-based and user-friendly

🛠️ Technologies Used

Python 3

requests library

OpenWeatherMap API

📌 How It Works

The user enters a city name.

The program sends a request to the OpenWeatherMap API.

Weather data is fetched in JSON format.

Data is parsed and displayed in a readable format.

If the city is invalid, an error message is displayed.

📂 Sample Code
import requests

city = input("Enter city name: ")
api_key = "YOUR_API_KEY"
url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric"

response = requests.get(url)
data = response.json()

if data["cod"] != "404":
    main = data["main"]
    wind = data["wind"]
    weather_desc = data["weather"][0]["description"]

    print(f"Weather in {city}:")
    print(f"Temperature: {main['temp']}°C")
    print(f"Humidity: {main['humidity']}%")
    print(f"Wind Speed: {wind['speed']} m/s")
    print(f"Condition: {weather_desc}")
else:
    print("City not found!")

📸 Example Output
Enter city name: Mumbai

Weather in Mumbai:
Temperature: 31°C
Humidity: 54%
Wind Speed: 3.5 m/s
Condition: Clear sky

🎯 Learning Outcomes

Using APIs in Python

Sending HTTP requests with requests module

Parsing JSON data

Handling user input

Building a simple real-time application

📁 Project Purpose

Perfect beginner-level project for learning Python and APIs

Can be added to GitHub portfolio

Useful for learning real-time data fetching

Helps prepare for Python-based interviews
