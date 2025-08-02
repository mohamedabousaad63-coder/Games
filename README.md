# Games
Guess the number game using HTML, CSS, and JavaScript.
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>لعبة تخمين الرقم</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="game-container">
    <h1>🎯 لعبة تخمين الرقم</h1>
    <p>اختر رقمًا بين 1 و 10</p>
    <input type="number" id="guess" min="1" max="10" placeholder="أدخل الرقم">
    <button onclick="checkGuess()">تحقق</button>
    <p id="result"></p>
    <button onclick="resetGame()">🔄 أعد اللعب</button>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Tahoma, sans-serif;
  background-color: #f0f0f0;
  direction: rtl;
  text-align: center;
  margin-top: 100px;
}
.game-container {
  background-color: #fff;
  padding: 30px;
  width: 300px;
  margin: auto;
  border-radius: 12px;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}
input[type="number"] {
  padding: 10px;
  width: 100px;
  border-radius: 5px;
  border: 1px solid #ccc;
  margin: 10px;
}
button {
  padding: 10px 20px;
  background-color: #008CBA;
  border: none;
  color: white;
  border-radius: 6px;
  cursor: pointer;
  margin-top: 10px;
}
button:hover {
  background-color: #007299;
}
#result {
  font-weight: bold
  let secretNumber = Math.floor(Math.random() * 10) + 1;

function checkGuess() {
  const guess = parseInt(document.getElementById("guess").value);
  const result = document.getElementById("result");

  if (isNaN(guess) || guess < 1 || guess > 10) {
    result.textContent = "🚫 من فضلك أدخل رقمًا بين 1 و 10";
    result.style.color = "red";
    return;
  }

  if (guess === secretNumber) {
    result.textContent = "🎉 صحيح! أحسنت التخمين!";
    result.style.color = "green";
  } else {
    result.textContent = "❌ خطأ! حاول مرة أخرى.";
    result.style.color = "red";
  }
}

function resetGame() {
  secretNumber = Math.floor(Math.random() * 10) + 1;
  document.getElementById("guess").value = "";
  document.getElementById("result").textContent = "";
}
