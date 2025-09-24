<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Site em Manutenção</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #1a2a6c, #b21f1f, #1a2a6c);
      color: white;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 20px;
    }

    .container {
      max-width: 600px;
      background: rgba(0, 0, 0, 0.75);
      padding: 40px;
      border-radius: 16px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    }

    h1 {
      font-size: 2.5rem;
      margin-bottom: 20px;
      color: #ffcc00;
    }

    p.subtitle {
      font-size: 1.2rem;
      margin-bottom: 25px;
      line-height: 1.6;
    }

    .countdown {
      font-size: 1.8rem;
      font-weight: bold;
      margin: 25px 0;
      color: #4fc3f7;
    }

    .countdown span {
      display: inline-block;
      min-width: 60px;
      padding: 8px 0;
      background: rgba(0, 0, 0, 0.4);
      border-radius: 8px;
      margin: 0 5px;
    }

    .menu {
      list-style: none;
      margin: 30px 0;
    }

    .menu li {
      margin: 15px 0;
    }

    .menu a {
      color: #4fc3f7;
      text-decoration: none;
      font-size: 1.1rem;
      display: inline-block;
      padding: 10px 20px;
      border: 1px solid #4fc3f7;
      border-radius: 8px;
      transition: all 0.3s ease;
    }

    .menu a:hover {
      background-color: #4fc3f7;
      color: #000;
      transform: translateY(-2px);
    }

    .footer {
      margin-top: 30px;
      font-size: 0.95rem;
      color: #bbb;
    }

    @media (max-width: 600px) {
      .container {
        padding: 25px;
      }

      h1 {
        font-size: 2rem;
      }

      .countdown {
        font-size: 1.4rem;
      }

      .countdown span {
        min-width: 45px;
        font-size: 1rem;
      }

      .menu a {
        font-size: 1rem;
        padding: 8px 16px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🛠️ Site em Manutenção</h1>
    <p class="subtitle">Estamos realizando melhorias para oferecer uma experiência ainda melhor!</p>

    <div class="countdown" id="countdown">
      <span id="hours">01</span>:
      <span id="minutes">30</span>:
      <span id="seconds">00</span>
    </div>

    <ul class="menu">
      <li><a href="#">&#127968; Página Inicial</a></li>
      <li><a href="mailto:contato@seudominio.com.br">&#128231; Contato</a></li>
      <li><a href="https://status.seudominio.com.br" target="_blank">&#128201; Status da Manutenção</a></li>
      <li><a href="https://seudominio.com.br">&#8617; Voltar ao Site</a></li>
    </ul>

    <div class="footer">
      <p><strong>Previsão de retorno:</strong> Em até 1 hora e 30 minutos.</p>
      <p>Agradecemos sua paciência. 😊</p>
    </div>
  </div>

  <script>
    // Define o tempo de manutenção: 1 hora e 30 minutos = 90 minutos = 5400 segundos
    let totalSeconds = 90 * 60; // 5400 segundos

    const hoursEl = document.getElementById('hours');
    const minutesEl = document.getElementById('minutes');
    const secondsEl = document.getElementById('seconds');

    function updateCountdown() {
      if (totalSeconds <= 0) {
        document.querySelector('.countdown').innerHTML = '<span style="color:#ff5252;">Manutenção concluída!</span>';
        clearInterval(timer);
        return;
      }

      const hours = Math.floor(totalSeconds / 3600);
      const minutes = Math.floor((totalSeconds % 3600) / 60);
      const seconds = totalSeconds % 60;

      hoursEl.textContent = String(hours).padStart(2, '0');
      minutesEl.textContent = String(minutes).padStart(2, '0');
      secondsEl.textContent = String(seconds).padStart(2, '0');

      totalSeconds--;
    }

    // Atualiza imediatamente ao carregar
    updateCountdown();

    // Atualiza a cada 1 segundo
    const timer = setInterval(updateCountdown, 1000);
  </script>
</body>
</html>
