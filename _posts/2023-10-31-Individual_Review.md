---
toc: false
comments: false
layout: post
title: Individual Review
description: Tri 1 Individual Review
courses: { compsci: { week: 11 } }
type: tangibles
---

<style>
  .bullet-points {
    list-style-type: disc; 
    margin-left: 40px; 
  }
  .bullet-points li {
    margin-bottom: 20px; 
  }
</style>

# Development Journey

---

### Getting data

Objective: Get real time stock data

<ul class = "bullet-points">
  <li>Approach: Use Yahoo Finance python module to get data</li>
  <li>Challenges: Need to handle multiple symbols, different date ranges (daily, monthly), and different types of data</li>
  <li>Problems faced: None</li>
</ul>

---

### Connecting frontend and backend

Objective: Send data from frontend to backend and get data

<ul class = "bullet-points">
  <li>Approach: Used JavaScript to send a request to the API with the GET method</li>
  <li>Challenges: JavaScript code was complicated and took a while to get working</li>
  <li>Problems faced: None</li>
</ul>

---

# Code Snippet

---

These are some code snippets I think show contribution to the code

### Python

This code snippet I worked on is how the data for the graph is created

```python
from flask import Blueprint, jsonify, request
import pandas as pd
import yfinance as yf
import plotly.graph_objs as go
from flask_restful import Api, Resource
import numpy as np
from flask_cors import CORS

stock_api = Blueprint('stock_api', __name__, url_prefix='/api/stocks')
api = Api(stock_api)

CORS(stock_api)


def get_stock_graph(stock_name):
    end_date = datetime.now()
    start_date = end_date - pd.Timedelta(days=4856)

    df = yf.download(stock_name, start=start_date, end=end_date)

    graph = go.Figure(data=go.Candlestick(x=df.index,
                                          open=df['Open'],
                                          high=df['High'],
                                          low=df['Low'],
                                          close=df['Close'],
                                          name=stock_name))
    graph.update_layout(title=f'{stock_name} Stock Price',
                        xaxis_title='Date',
                        yaxis_title='Price')

    graph_data = graph.to_dict()
    graph_data['data'][0]['x'] = graph_data['data'][0]['x'].astype(
        str).tolist()
    graph_data['data'][0]['open'] = graph_data['data'][0]['open'].tolist()
    graph_data['data'][0]['high'] = graph_data['data'][0]['high'].tolist()
    graph_data['data'][0]['low'] = graph_data['data'][0]['low'].tolist()
    graph_data['data'][0]['close'] = graph_data['data'][0]['close'].tolist()

    return graph_data


class _ReadStockGraph(Resource):
    def get(self, stock_name):
        graph = get_stock_graph(stock_name)
        return graph

```

### JavaScript

This is the code that connects the backend and frontend Via JavaScript to send a request for the graph data and plots it

```python
%%js
function getStockGraph() {
            const selectedStock = document.getElementById('stock-input').value;
            const button = document.getElementById('collect');
            const apiUrl = 'http://localhost:8282/api/stocks/stock_graph/' + selectedStock;
            button.textContent = 'Loading...';
            fetch(apiUrl)
                .then(response => response.json())
                .then(graphData => {
                    Plotly.newPlot('graph', graphData.data, graphData.layout);
                    button.textContent = 'Display Graph';
                })
                .catch(error => {
                    console.error('Error:', error);
                    button.textContent = 'Display Graph';
                });
        }
        const stockInput = document.getElementById('stock-input');
        const collectButton = document.getElementById('collect');
        stockInput.addEventListener("keydown", function (event) {
            if (event.key === 'Enter') {
                getStockGraph();
            }
        });
        collectButton.addEventListener("click", getStockGraph);
```

# Github Analytics

### Key Commits:

<ul class = "bullet-points">
  <li>Creating backend code for the graph</li>
  <li>Connecting frontend and backend for the graph</li>
  <li>Working on a lot of the portfolio Optimizer</li>
</ul>

### Issues:

<ul class = "bullet-points">
  <li>Connecting Frontend and Backend took a long time </li>
</ul>

---

# Individual Blog

### Snippet from Simulations team teach

```python
Hack: Given initial parameters for a car simulation, including its initial speed, acceleration rate, deceleration rate, maximum speed, and initial distance, write a program to simulate the car’s journey and determine the final speed, distance covered, and time taken before it either covers 1000 meters or slows down to below 5 m/s?
```

```python
initial_speed = 10
acceleration_rate = 2
deceleration_rate = -1
max_speed = 20
initial_distance = 0
target_distance = 1000
min_speed = 5

speed = initial_speed
distance = initial_distance
time = 0

while distance < target_distance and speed >= min_speed:
    time_to_max_speed = (max_speed - speed) / acceleration_rate
    distance_covered_acceleration = speed * time_to_max_speed + 0.5 * acceleration_rate * time_to_max_speed ** 2

    if distance + distance_covered_acceleration >= target_distance:
        time += (-speed + (speed ** 2 + 2 * acceleration_rate * (target_distance - distance)) ** 0.5) / acceleration_rate
        speed = max_speed
        distance = target_distance
    else:
        time += time_to_max_speed
        speed = max_speed
        distance += distance_covered_acceleration

        if distance < target_distance:
            time_to_decelerate = (speed - min_speed) / abs(deceleration_rate)
            distance_covered_deceleration = speed * time_to_decelerate + 0.5 * deceleration_rate * time_to_decelerate ** 2

            if distance + distance_covered_deceleration >= target_distance:
                time += (-speed + (speed ** 2 - 2 * deceleration_rate * (distance - target_distance)) ** 0.5) / abs(deceleration_rate)
                speed = min_speed
                distance = target_distance
            else:
                time += time_to_decelerate
                speed = min_speed
                distance += distance_covered_deceleration

print(f"Final Speed: {speed} m/s")
print(f"Distance Covered: {distance} meters")
print(f"Time Taken: {time} seconds")
```

# Trimester One Reflections

- Throughout this trimester, I've gained valuable insights and acquired new skills, ranging from project planning to data retrieval from a backend repository through an API uses Python modules like Yahoo Finance and scikit-learn. I did this using JavaScript to fetch a response in JSON data. Some achievements include successfully establishing the connection between a frontend and backend repository using the 'fetch' command. I've also gained practical experience in HTML, JavaScript, and Python.

- Moreover, I've gained a solid understanding of APIs and their functionality, which I hope will be beneficial in my future endeavors. In addition to my accomplishments, I recognize certain areas for potential growth. Specifically, I aim to enhance my frontend web design skills by leveraging HTML to create more polished website layouts. While I have a foundational understanding of web design, I am eager to delve deeper into this subject.

- Furthermore, I am committed to expanding my knowledge of APIs and improving my proficiency with the 'fetch' command, as I am genuinely intrigued by the capability to retrieve data from one source and seamlessly transfer it to another. This reflection encapsulates the progress and aspirations I have for my first trimester's journey.

### Memories and Learning:

<ul class = "bullet-points">
  <li> Agile development process</li>
  <li> Learning how to work in groups to create a large project</li>
  <li> Working on and debugging Code especially Python and JavaScript</li>
  <li> Helping out other groups with code issues</li>
</ul>

### Positive Accomplishments

<ul class = "bullet-points">
  <li> Working on backend and frontend development to create a full stack web project</li>
  <li> Implementing the Flask framework for our website</li>
  <li> Learning and using new tools and programs</li>
</ul>

### Opportunites for Growth and things I hope to learn in Tri 2

<ul class = "bullet-points">
  <li> Debugging code. Espescially with breakpoints</li>
  <li> Deepen CompSci knowledge with backend data</li>
  <li> More about API's and creating full stack web apps</li>
  <li> Become more fluent and comfortable with the CLI</li>
</ul>
