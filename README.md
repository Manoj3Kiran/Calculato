<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            margin: 0;
        }

        .calculator {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .display {
            width: 100%;
            height: 50px;
            font-size: 24px;
            text-align: right;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f9f9f9;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .button {
            background-color: #333;
            color: #fff;
            border: none;
            border-radius: 5px;
            padding: 20px;
            font-size: 18px;
            cursor: pointer;
        }

        .button:hover {
            background-color: #555;
        }

        .button.operation {
            background-color: #ff9800;
        }

        .button.operation:hover {
            background-color: #e68a00;
        }

        .button.equal {
            grid-column: span 2;
            background-color: #4caf50;
        }

        .button.equal:hover {
            background-color: #45a045;
        }

        .button.clear {
            background-color: #f44336;
        }

        .button.clear:hover {
            background-color: #d73833;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="buttons">
            <button class="button" onclick="appendToDisplay('7')">7</button>
            <button class="button" onclick="appendToDisplay('8')">8</button>
            <button class="button" onclick="appendToDisplay('9')">9</button>
            <button class="button operation" onclick="appendToDisplay('/')">/</button>

            <button class="button" onclick="appendToDisplay('4')">4</button>
            <button class="button" onclick="appendToDisplay('5')">5</button>
            <button class="button" onclick="appendToDisplay('6')">6</button>
            <button class="button operation" onclick="appendToDisplay('*')">*</button>

            <button class="button" onclick="appendToDisplay('1')">1</button>
            <button class="button" onclick="appendToDisplay('2')">2</button>
            <button class="button" onclick="appendToDisplay('3')">3</button>
            <button class="button operation" onclick="appendToDisplay('-')">-</button>

            <button class="button" onclick="appendToDisplay('0')">0</button>
            <button class="button" onclick="appendToDisplay('.')">.</button>
            <button class="button equal" onclick="calculate()">=</button>
            <button class="button operation" onclick="appendToDisplay('+')">+</button>

            <button class="button clear" onclick="clearDisplay()">C</button>
        </div>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculate() {
            const display = document.getElementById('display');
            try {
                display.value = eval(display.value);
            } catch {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
