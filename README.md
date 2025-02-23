<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Калькулятор</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f9;
            margin: 0;
        }
        .calculator {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            width: 300px;
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
            box-sizing: border-box;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        .button {
            background-color: #f9f9f9;
            border: 1px solid #ccc;
            padding: 20px;
            font-size: 18px;
            text-align: center;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .button:hover {
            background-color: #e0e0e0;
        }
        .button.operator {
            background-color: #ff9500;
            color: white;
        }
        .button.operator:hover {
            background-color: #e08900;
        }
        .button.clear {
            background-color: #ff3b30;
            color: white;
            grid-column: span 2;
        }
        .button.clear:hover {
            background-color: #e02a20;
        }
        .button.equal {
            background-color: #34c759;
            color: white;
            grid-column: span 2;
        }
        .button.equal:hover {
            background-color: #2da94f;
        }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" class="display" id="display" disabled>
    <div class="buttons">
        <div class="button clear" onclick="clearDisplay()">C</div>
        <div class="button operator" onclick="appendOperator('/')">/</div>
        <div class="button operator" onclick="appendOperator('*')">*</div>
        <div class="button" onclick="appendNumber(7)">7</div>
        <div class="button" onclick="appendNumber(8)">8</div>
        <div class="button" onclick="appendNumber(9)">9</div>
        <div class="button operator" onclick="appendOperator('-')">-</div>
        <div class="button" onclick="appendNumber(4)">4</div>
        <div class="button" onclick="appendNumber(5)">5</div>
        <div class="button" onclick="appendNumber(6)">6</div>
        <div class="button operator" onclick="appendOperator('+')">+</div>
        <div class="button" onclick="appendNumber(1)">1</div>
        <div class="button" onclick="appendNumber(2)">2</div>
        <div class="button" onclick="appendNumber(3)">3</div>
        <div class="button equal" onclick="calculate()">=</div>
        <div class="button" onclick="appendNumber(0)">0</div>
        <div class="button" onclick="appendNumber('.')">.</div>
    </div>
</div>

<script>
    let display = document.getElementById('display');

    // Добавление числа на экран
    function appendNumber(number) {
        display.value += number;
    }

    // Добавление оператора на экран
    function appendOperator(operator) {
        display.value += operator;
    }

    // Очистка экрана
    function clearDisplay() {
        display.value = '';
    }

    // Вычисление результата
    function calculate() {
        try {
            display.value = eval(display.value);
        } catch (e) {
            display.value = 'Ошибка';
        }
    }
</script>

</body>
</html>
