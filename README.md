<!DOCTYPE html>
<html>
<head>
    <title>Enhanced Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
            background-color: #f3f3f3;
        }
        #calculator {
            display: inline-block;
            padding: 20px;
            border: 2px solid #4caf50;
            border-radius: 10px;
            background-color: #ffffff;
            box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
        }
        input[type="text"] {
            width: 240px;
            height: 40px;
            margin-bottom: 10px;
            font-size: 20px;
            text-align: right;
            border-radius: 5px;
            border: 2px solid #ccc;
            padding: 5px;
        }
        button {
            width: 55px;
            height: 55px;
            font-size: 18px;
            margin: 5px;
            border-radius: 5px;
            background-color: #4caf50;
            color: white;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>Enhanced Calculator</h1>
    <div id="calculator">
        <input type="text" id="display" disabled><br>
        <button onclick="append('1')">1</button>
        <button onclick="append('2')">2</button>
        <button onclick="append('3')">3</button>
        <button onclick="append('+')">+</button><br>
        <button onclick="append('4')">4</button>
        <button onclick="append('5')">5</button>
        <button onclick="append('6')">6</button>
        <button onclick="append('-')">-</button><br>
        <button onclick="append('7')">7</button>
        <button onclick="append('8')">8</button>
        <button onclick="append('9')">9</button>
        <button onclick="append('*')">×</button><br>
        <button onclick="clearDisplay()">C</button>
        <button onclick="append('0')">0</button>
        <button onclick="calculate()">=</button>
        <button onclick="append('/')">÷</button><br>
        <button onclick="append('**2')">x²</button>
        <button onclick="append('**0.5')">√</button>
        <button onclick="append('%')">%</button>
        <button onclick="backspace()">⌫</button>
    </div>

    <script>
        function append(value) {
            document.getElementById("display").value += value;
        }

        function clearDisplay() {
            document.getElementById("display").value = "";
        }

        function calculate() {
            try {
                const result = eval(document.getElementById("display").value);
                document.getElementById("display").value = result;
            } catch (error) {
                alert("Invalid input!");
            }
        }

        function backspace() {
            const display = document.getElementById("display");
            display.value = display.value.slice(0, -1);
        }
    </script>
</body>
</html>
