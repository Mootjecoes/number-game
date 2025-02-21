# number-game  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number Guessing Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        #gameContainer {
            margin-top: 20px;
        }
        .result {
            font-size: 20px;
            font-weight: bold;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>Guess the Number Game</h1>
    <p>Try to guess the number between 1 and 100!</p>

    <div id="gameContainer">
        <input type="number" id="userGuess" placeholder="Enter a number" />
        <button onclick="checkGuess()">Guess</button>
        <p id="resultMessage" class="result"></p>
        <p>Number of attempts: <span id="attemptCount">0</span></p>
    </div>

    <script src="game.js"></script>
</body>
</html>
// game.js

// Generate a random number between 1 and 100
const randomNumber = Math.floor(Math.random() * 100) + 1;
let attempts = 0;

function checkGuess() {
    const userGuess = parseInt(document.getElementById('userGuess').value);
    const resultMessage = document.getElementById('resultMessage');
    const attemptCount = document.getElementById('attemptCount');
    
    attempts++;
    attemptCount.textContent = attempts;

    if (userGuess === randomNumber) {
        resultMessage.textContent = `Congratulations! You guessed the right number: ${randomNumber}`;
        resultMessage.style.color = "green";
    } else if (userGuess > randomNumber) {
        resultMessage.textContent = "Too high! Try again.";
        resultMessage.style.color = "red";
    } else if (userGuess < randomNumber) {
        resultMessage.textContent = "Too low! Try again.";
        resultMessage.style.color = "red";
    }
}
