<!DOCTYPE html>
<html>
<head>
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }
        #calculator {
            display: inline-block;
            padding: 20px;
            border: 2px solid #ccc;
            border-radius: 8px;
            background-color: #f9f9f9;
        }
        input[type="text"] {
            width: 200px;
            height: 30px;
            margin-bottom: 10px;
            font-size: 18px;
            text-align: right;
        }
        button {
            width: 48px;
            height: 48px;
            font-size: 18px;
            margin: 5px;
        }
    </style>
</head>
<body>
    <h1>Simple Calculator</h1>
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
        <button onclick="append('*')">x</button><br>
        <button onclick="clearDisplay()">C</button>
        <button onclick="append('0')">0</button>
        <button onclick="calculate()">=</button>
        <button onclick="append('/')">/</button>
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
    </script>
</body>
</html>
