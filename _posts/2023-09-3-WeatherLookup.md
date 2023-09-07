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
    function fetchWeather() {
      var locationInput = document.getElementById("location");
      var location = locationInput.value.trim();

      if (location === "") {
        alert("Please enter a city.");
        return;
      }

      var OpenWeatherMapAPIKey = "06ffac091aa8f9ef15e54c9209611dcd";

      var URL = `https://api.openweathermap.org/data/2.5/weather?q=${location}&appid=${OpenWeatherMapAPIKey}`;
      

      fetch(URL)
        .then(response => response.json())
        .then(data => {

          if (data.sys) {
            var weatherContainer = document.getElementById("weather-data");
            var temperature = Math.round(((data.main.temp - 273.15) * (9 / 5)) + 32).toFixed(0);
            weatherContainer.innerHTML = `
                    <br>
                    <h2>Weather in ${data.name}, ${data.sys.country} looks like:</h2>
                    <p>Temperature: ${temperature}°F,  ${data.weather[0].description}</p>
                    <p>Humidity is ${data.main.humidity}%</p>
                `;
          } else {
            console.error("Error fetching weather data: Country information not available.");
            alert('Please try retyping the city name');
          }
        })
        .catch(error => {
          console.error("Error fetching weather data:", error);
        });
    }
    var locationInput = document.getElementById("location");
    locationInput.addEventListener("keyup", function (event) {
      if (event.key === "Enter") {
        fetchWeather();
      }
    });
  </script>

</body>
