<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Um convite para você 💗</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #ffd6e7, #ffeef5);
      color: #5a2940;
      padding: 20px;
    }

    .card {
      width: 100%;
      max-width: 480px;
      background: white;
      padding: 30px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 10px 30px rgba(150, 60, 100, 0.2);
    }

    .heart {
      font-size: 55px;
      animation: pulsar 1.3s infinite;
    }

    @keyframes pulsar {
      50% {
        transform: scale(1.15);
      }
    }

    h1 {
      color: #e75480;
      margin-bottom: 8px;
    }

    .subtitle {
      font-size: 17px;
      margin-bottom: 25px;
    }

    .section {
      margin: 22px 0;
    }

    h2 {
      font-size: 19px;
      color: #d94f78;
    }

    .options {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
    }

    button {
      border: none;
      padding: 12px 17px;
      border-radius: 15px;
      background: #ffe0eb;
      color: #8b3657;
      font-size: 15px;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      transform: scale(1.05);
      background: #ffb8d0;
    }

    button.selected {
      background: #e75480;
      color: white;
    }

    #confirmar {
      margin-top: 15px;
      width: 100%;
      background: #e75480;
      color: white;
      font-size: 18px;
      font-weight: bold;
      padding: 15px;
    }

    #resultado {
      margin-top: 20px;
      padding: 15px;
      border-radius: 15px;
      background: #fff0f6;
      display: none;
      line-height: 1.6;
    }

    .small {
      font-size: 13px;
      color: #8b6473;
      margin-top: 20px;
    }
  </style>
</head>

<body>

  <div class="card">

    <div class="heart">💗</div>

    <h1>Eduarda, tenho um convite! 🥰</h1>

    <p class="subtitle">
      Que tal a gente sair juntos? 👀💕<br>
      Você escolhe quando e onde!
    </p>

    <div class="section">
      <h2>📅 Escolha o dia</h2>

      <div class="options">
        <button onclick="selecionar(this, 'dia')">Dia 19</button>
        <button onclick="selecionar(this, 'dia')">Dia 20</button>
        <button onclick="selecionar(this, 'dia')">Dia 26</button>
      </div>
    </div>

    <div class="section">
      <h2>⏰ Escolha o horário</h2>

      <div class="options">
        <button onclick="selecionar(this, 'hora')">11:00 - 14:00 ☀️</button>
        <button onclick="selecionar(this, 'hora')">20:00 - 23:00 🌙</button>
      </div>
    </div>

    <div class="section">
      <h2>📍 Onde vamos?</h2>

      <div class="options">
        <button onclick="selecionar(this, 'local')">🎬 Cinema</button>
        <button onclick="selecionar(this, 'local')">🥪 Subway</button>
        <button onclick="selecionar(this, 'local')">🛍️ Shopping</button>
      </div>
    </div>

    <button id="confirmar" onclick="confirmar()">
      💕 Aceitar o convite!
    </button>

    <div id="resultado"></div>

    <p class="small">
      P.S.: escolher "sim" é altamente recomendado 😌💗
    </p>

  </div>

  <script>
    let escolhas = {
      dia: "",
      hora: "",
      local: ""
    };

    function selecionar(botao, tipo) {
      const botoes = botao.parentElement.querySelectorAll("button");

      botoes.forEach(b => b.classList.remove("selected"));

      botao.classList.add("selected");

      escolhas[tipo] = botao.innerText;
    }

    function confirmar() {

      if (!escolhas.dia || !escolhas.hora || !escolhas.local) {
        alert("Calmaaa 😭💗 Escolhe o dia, horário e lugar primeiro!");
        return;
      }

      const resultado = document.getElementById("resultado");

      resultado.style.display = "block";

      resultado.innerHTML = `
        <strong>AAAAA, temos um encontro marcado! 💕🥰</strong>
        <br><br>
        📅 ${escolhas.dia}<br>
        ⏰ ${escolhas.hora}<br>
        📍 ${escolhas.local}
        <br><br>
        Mal posso esperar! 💗✨
      `;
    }
  </script>

</body>
</html>
