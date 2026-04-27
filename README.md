# Myfirstcode
This is a basic, responsive calculator created using HTML, CSS, and JavaScript. It allows users to perform simple arithmetic operations: addition, subtraction, multiplication, and division.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f8f8f8;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      width: 260px;
    }
    .display {
      width: 100%;
      font-size: 2em;
      height: 50px;
      text-align: right;
      padding: 10px;
      border: none;
      background: #f3f3f3;
      margin-bottom: 10px;
      border-radius: 8px;
      box-sizing: border-box;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    .buttons button {
      padding: 15px;
      font-size: 1.2em;
      border: none;
      border-radius: 8px;
      background: #e7e7e7;
      cursor: pointer;
      transition: background 0.2s;
    }
    .buttons button.operator {
      background: #55b6ff;
      color: #fff;
    }
    .buttons button.equal {
      background: #28c76f;
      color: #fff;
      grid-column: span 2;
    }
    .buttons button.clear {
      background: #ff5a5f;
      color: #fff;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled />
    <div class="buttons">
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('/')" class="operator">÷</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('*')" class="operator">×</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('-')" class="operator">−</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendValue('+')" class="operator">+</button>

      <button onclick="calculate()" class="equal">=</button>
    </div>
  </div>
  <script>
    function appendValue(val) {
      const display = document.getElementById('display');
      display.value += val;
    }

    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function calculate() {
      const display = document.getElementById('display');
      try {
        display.value = eval(display.value.replace(/÷/g,'/').replace(/×/g,'*'));
      } catch (e) {
        display.value = 'Error';
      }
    }
  </script>
</body>
</html>
