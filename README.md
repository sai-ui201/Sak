<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Color Trading Simulator</title>
  <style>
    body {
      font-family: Arial;
      text-align: center;
      padding: 40px;
    }
    #colorBox {
      width: 150px;
      height: 150px;
      margin: 20px auto;
      border: 3px solid #ccc;
      border-radius: 10px;
    }
    button {
      padding: 10px 20px;
      margin: 5px;
      font-size: 18px;
    }
    #result {
      font-size: 20px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Color Trading Game</h1>
  <p>Predict the next color (Red, Green, or Violet)</p>
  <button onclick="predict('Red')">Red</button>
  <button onclick="predict('Green')">Green</button>
  <button onclick="predict('Violet')">Violet</button>

  <div id="colorBox"></div>
  <p id="result"></p>

  <script>
    const colors = ['Red', 'Green', 'Violet'];

    function getRandomColor() {
      const randIndex = Math.floor(Math.random() * colors.length);
      return colors[randIndex];
    }

    function predict(userChoice) {
      const actualColor = getRandomColor();
      document.getElementById('colorBox').style.backgroundColor = actualColor.toLowerCase();

      if (userChoice === actualColor) {
        document.getElementById('result').innerText = `✅ Correct! It was ${actualColor}.`;
      } else {
        document.getElementById('result').innerText = `❌ Wrong! It was ${actualColor}.`;
      }
    }
  </script>
</body>
</html>
