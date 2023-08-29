---
layout: default
title: Imaad's Page
---


## Who am I?
My name is Imaad Muzaffer and I am a passionate coder who loves working his way around problems. I belive that you have to approach coding with a curious and embracing mindset. I enjoy embracing coding problems because each time I encounter a problem, I see it as a way to broaden my coding skillset and become a better coder in general. Another thing I love about coding, web development, specifically, is when you pour a lot of hard work into a website and it turns out looking exactly how you want. Frienship is also something I hold extremely close to me as I love being around my friends and laughing with them. This feeling makes me feel happy and brings a smile to my face. 
- I specialize in web development with HTML/CSS/Javascript as well as game development with Unity. You can check out my projects here including a calcualtor:

### GitHub Account
My [Github Account](https://github.com/Imaad08){:target="_blank"} where I host my websites and games.

### Unity Game
<!-- My [Unity game hosted with Github Pages](https://imaad08.github.io/FlippyMazeGame/){:target="_blank"}(computer only)
- Youtube video of the game:
<iframe width="560" height="315" src="https://www.youtube.com/embed/l5y0hlhtjbY" frameborder="0" allowfullscreen></iframe> -->


<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Imaad's Game</title>
</head>
<body>
  <div id="unityContainer"></div>
  <iframe src="FlippyMazeGame/index.html" width="1000" height="650"></iframe>
  <div id="unityContainer"></div>
  <script src="FlippyMazeGame/TemplateData/UnityProgress.js"></script>
  <script src="FlippyMazeGame/Build/UnityLoader.js"></script>
  <script>
    var container = document.getElementById("unityContainer");
    var gameInstance = UnityLoader.instantiate(container, "path-to-your-unity-game/Build/YourGame.json");
  </script>
</body>
</html> 


### Calculator

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Imaad's Calculator</title>
  <style>
    button {
      cursor: pointer;
      font-size: 2rem;
      border: 1px solid grey;
      outline: none;
      background-color: rgba(255, 255, 255, .75);
    }
    button:hover {
      background-color: grey;
    }
    .operator {
      background-color: #f2a154;
      color: white;
    }
    .calculator {
      display: grid;
      justify-content: center;
      align-content: center;
      min-height: 50vh;
      grid-template-columns: repeat(4, 100px);
      grid-template-rows: minmax(120px, auto) repeat(5, 100px);
    }
    .two-spaces {
      grid-column: span 2;
    }
    .three-spaces {
      grid-column: span 3;
    }
    .display {
      grid-column: 1 / -1;
      background-color: rgba(0, 0, 0, .75);
      display: flex;
      align-items: flex-end;
      justify-content: space-around;
      flex-direction: column;
      padding: 10px;
      word-wrap: break-word;
      word-break: break-all;
    }
    input {
      width: 100%;
      border: none;
      font-size: 1.5rem;
      background-color: transparent;
      color: white;
    }
  </style>
</head>

<body>
  <div class="calculator">
    <div class="display">
      <input type="text" id="result" value="0" disabled>
    </div>
    <button id="clear" class="three-spaces" onclick="clearDisplay()">AC</button>
    <button class="operator" onclick="appendSymbol('/')">÷</button>
    <button onclick="appendSymbol('1')">1</button>
    <button onclick="appendSymbol('2')">2</button>
    <button onclick="appendSymbol('3')">3</button>
    <button class="operator" onclick="appendSymbol('*')">*</button>
    <button onclick="appendSymbol('4')">4</button>
    <button onclick="appendSymbol('5')">5</button>
    <button onclick="appendSymbol('6')">6</button>
    <button class="operator" onclick="appendSymbol('+')">+</button>
    <button onclick="appendSymbol('7')">7</button>
    <button onclick="appendSymbol('8')">8</button>
    <button onclick="appendSymbol('9')">9</button>
    <button class="operator" onclick="appendSymbol('-')">-</button>
    <button onclick="appendSymbol('.')">.</button>
    <button onclick="appendSymbol('0')">0</button>
    <button id="equals" class="two-spaces" onclick="calculate()">=</button>
  </div>
  <script>
    let currentInput = '';
    function appendSymbol(symbol) {
      currentInput += symbol;
      updateDisplay(currentInput);
    }
    function calculate() {
      try {
        const result = eval(currentInput);
        updateDisplay(result);
        currentInput = result.toString();
      } catch (error) {
        updateDisplay('Error');
        currentInput = '';
      }
    }
    function clearDisplay() {
      currentInput = '';
      updateDisplay('0');
    }
    function updateDisplay(content) {
      document.getElementById('result').value = content;
    }


  </script>
</body>



## My Class Schedule:
<table style="border-collapse: collapse; width: 50%;">
  <tr>
    <th style="border: 1px solid black; padding: 8px;">Period</th>
    <th style="border: 1px solid black; padding: 8px;">Class</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">1</td>
    <td style="border: 1px solid black; padding: 8px;">3D Computer Animation 2</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">2</td>
    <td style="border: 1px solid black; padding: 8px;">AP Chemistry</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">3</td>
    <td style="border: 1px solid black; padding: 8px;">AP Calculus AB</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">4</td>
    <td style="border: 1px solid black; padding: 8px;">World History 1</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">5</td>
    <td style="border: 1px solid black; padding: 8px;">AP CSP</td>
  </tr>
</table>

## Pictures about me:
 

| <img src="https://i.ibb.co/c88RFfS/IMG-6520.jpg" width="auto" height="400"> | ![Image 2](https://i.ibb.co/XjgxswZ/Full-Size-Render.jpg) |
|:---:|:---:|
| This is my picture I created with freeform that expresses myself. | I value relationships with my friends and family very highly. |

