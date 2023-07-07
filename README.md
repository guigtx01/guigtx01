<html>
<head>
  <meta charset="UTF-8">
  <title>Cuzinho Domingo?</title>
  <style>
    body {
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      height: 100vh;
      margin: 0;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    
    h2 {
      font-size: 24px;
    }
    
    .question-text {
      font-size: 24px;
      color: white;
      border: 2px solid purple;
      padding: 10px;
    }
    
    .button-container {
      margin-top: 20px;
    }
    
    .button {
      display: inline-block;
      padding: 10px 20px;
      margin: 10px;
      background-color: white;
      color: blue;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    
    .blink-bg {
      animation: blinking-bg 1s infinite alternate;
    }
    
    @keyframes blinking-bg {
      0% { background-color: red; }
      25% { background-color: green; }
      50% { background-color: yellow; }
      75% { background-color: orange; }
      100% { background-color: red; }
    }
    
    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <div class="question">
    <h2 class="question-text">Cuzinho Domingo?</h2>
    <div class="button-container">
      <button class="button" id="sim">Sim</button>
      <button class="button" id="nao">Não</button>
    </div>
  </div>

  <div id="response" class="hidden">
    <h1 class="blink-bg">Resposta recebida!</h1>
    <h2 class="blink-bg">Te aguardo domingo</h2>
  </div>

  <script>
    var naoButton = document.getElementById("nao");
    var responseDiv = document.getElementById("response");

    naoButton.addEventListener("click", function() {
      var randomX = Math.floor(Math.random() * (window.innerWidth - naoButton.offsetWidth));
      var randomY = Math.floor(Math.random() * (window.innerHeight - naoButton.offsetHeight));
      
      naoButton.style.position = "absolute";
      naoButton.style.left = randomX + "px";
      naoButton.style.top = randomY + "px";
    });

    document.getElementById("sim").addEventListener("click", function() {
      document.body.style.background = "black";
      document.body.style.justifyContent = "center";
      responseDiv.classList.remove("hidden");
      naoButton.style.display = "none";
    });
  </script>
</body>
</html>
