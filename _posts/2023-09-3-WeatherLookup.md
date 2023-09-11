---
toc: false
comments: true
layout: post
title: Weather Lookup
description: Shows weather of any city using an OpenWeatherMap API key
courses: { compsci: {week: 3} }
type: hacks
---

# Weather lookup:

---

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Weather App</title>
  <style>
    .container {
      text-align: center;
      background-color: #fff;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    }
    h1 {
      color: #333;
    }
    .search-container {
      margin: 20px 0;
      border-radius: 20px;
    }
    input[type="text"] {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 20px;
    }
    button {
      padding: 10px 20px;
      background-color: #007bff;
      color: #fff;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #0056b3;
    }
  </style>
</head>

<body>


  <div class="weather-container">
    <input type="text" id="location" placeholder="Enter a city">
    <button onclick="fetchWeather()">Search</button>
    <div id="weather-data">
    </div>
  </div>

  <script>
// Function to fetch weather data when called
function fetchWeather() {
  // Get the input element for location from the HTML document
  var locationInput = document.getElementById("location");

  // Get the trimmed value of the location input
  var location = locationInput.value.trim();

  // Check if the location input is empty
  if (location === "") {
    // Display an alert if the input is empty and return from the function
    alert("Please enter a city.");
    return;
  }

  // OpenWeatherMap API Key for authentication
  var OpenWeatherMapAPIKey = "06ffac091aa8f9ef15e54c9209611dcd";

  // Construct the URL for the OpenWeatherMap API request using the location and API key
  var URL = `https://api.openweathermap.org/data/2.5/weather?q=${location}&appid=${OpenWeatherMapAPIKey}`;

  // Use the fetch API to make an HTTP request to the OpenWeatherMap API
  fetch(URL)
    .then(response => response.json()) // Parse the response as JSON
    .then(data => {
      // Check if the data includes sys information, indicating a valid response
      if (data.sys) {
        // Get the weather data container element from the HTML document
        var weatherContainer = document.getElementById("weather-data");

        // Calculate the temperature in Fahrenheit from the Kelvin value in the response
        var temperature = Math.round(((data.main.temp - 273.15) * (9 / 5)) + 32).toFixed(0);

        // Update the HTML content with weather information
        weatherContainer.innerHTML = `
          <br>
          <h2>Weather in ${data.name}, ${data.sys.country} looks like:</h2>
          <p>Temperature: ${temperature}°F, ${data.weather[0].description}</p>
          <p>Humidity is ${data.main.humidity}%</p>
        `;
      } else {
        // If sys information is not available in the response, log an error and show an alert
        console.error("Error fetching weather data: Country information not available.");
        alert('Please try retyping the city name');
      }
    })
    .catch(error => {
      // Handle any errors that occur during the fetch operation
      console.error("Error fetching weather data:", error);
    });
}

// Get the location input element again
var locationInput = document.getElementById("location");

// Add an event listener to the location input element to trigger fetchWeather() when Enter key is pressed
locationInput.addEventListener("keyup", function (event) {
  if (event.key === "Enter") {
    fetchWeather();
  }
});

  </script>

</body>
