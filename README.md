<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Professional Kalkulyator</title>
    <style>
        body { font-family: sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; background-color: #f4f4f9; margin: 0; }
        .calculator { background: #333; padding: 20px; border-radius: 15px; box-shadow: 0 10px 20px rgba(0,0,0,0.3); width: 300px; }
        #display { width: 100%; height: 50px; font-size: 24px; text-align: right; margin-bottom: 10px; padding: 10px; box-sizing: border-box; border: none; border-radius: 5px; }
        .buttons { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; }
        button { padding: 20px; font-size: 18px; border: none; border-radius: 8px; cursor: pointer; background: #555; color: white; transition: 0.2s; }
        button:hover { background: #777; }
        .operator { background: #f39c12; }
        .equals { background: #27ae60; grid-column: span 2; }
        .clear { background: #c0392b; grid-column: span 2; }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button class="operator" onclick="appendToDisplay('/')">/</button>
        <button class="operator" onclick="appendToDisplay('*')">×</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button class="operator" onclick="appendToDisplay('-')">-</button>
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button class="operator" onclick="appendToDisplay('+')">+</button>
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="appendToDisplay('.')">.</button>
        <button class="equals" onclick="calculate()">=</button>
    </div>
</div>

<script>
    const display = document.getElementById('display');

    function appendToDisplay(input) {
        display.value += input;
    }

    function clearDisplay() {
        display.value = "";
    }

    function calculate() {
        try {
            // eval() xavfsizlik uchun faqat shaxsiy loyihalarda ishlatiladi
            display.value = eval(display.value);
        } catch (error) {
            display.value = "Xato";
        }
    }
</script>

</body>
</html>
