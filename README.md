<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Calculator</title>
  <style>
    body {
      background: #f0f0f0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
    }
    input {
      width: 100%;
      height: 60px;
      font-size: 24px;
      margin-bottom: 10px;
      text-align: right;
      padding-right: 10px;
      border: 2px solid #ccc;
      border-radius: 8px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 70px);
      gap: 10px;
    }
    button {
      padding: 15px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      background: #eee;
      transition: background 0.3s;
    }
    
    button:hover {
      background: #ddd;
    }
    .equal { background: #4caf50; color: white; }
    .clear { background: #f44336; color: white; }
  </style>
</head>
<body>

  <div class="calculator">
    
    <input type="text" id="display" readonly>
    <div class="buttons">
      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button onclick="append('/')">/</button>

      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button onclick="append('*')">*</button>

      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button onclick="append('-')">-</button>

      <button onclick="append('0')">0</button>
      <button onclick="append('.')">.</button>
      <button onclick="calculate()" class="equal">=</button>
      <button onclick="append('+')">+</button>

      <button onclick="clearDisplay()" class="clear">C</button>
      <button class="operator" onclick="append('(')">(</button>
      <button class="operator" onclick="append(')')">)</button>
      <button class="operator" onclick="append('%')">%</button>
    </div>
  </div>

  <script>
    function append(value) {
      document.getElementById('display').value += value;
    }
    function clearDisplay() {
      document.getElementById('display').value = '';
    }
    function calculate() {
      try {
        document.getElementById('display').value = 
          eval(document.getElementById('display').value);
      } catch {
        alert("Invalid Expression");
      }
    }
  </script>
</body>
</html>
