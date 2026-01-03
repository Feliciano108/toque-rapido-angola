
🎮 Fortuna Colorida – Jogo Web

<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fortuna Colorida</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #ff0080, #7928ca);
      color: white;
      text-align: center;
      overflow: hidden;
    }
    h1 { margin-top: 15px; }
    #score, #coins { font-size: 18px; }
    #gameArea {
      position: relative;
      width: 100vw;
      height: 80vh;
    }
    .circle {
      position: absolute;
      width: 60px;
      height: 60px;
      border-radius: 50%;
      animation: pop 0.3s ease;
    }
    @keyframes pop {
      from { transform: scale(0); }
      to { transform: scale(1); }
    }
    #footer {
      font-size: 12px;
      opacity: 0.8;
    }
  </style>
</head>
<body>
  <h1>🎮 Fortuna Colorida</h1>
  <div id="score">Pontos: 0</div>
  <div id="coins">Moedas: 0 🪙</div>

  <div id="gameArea"></div>

  <p id="footer">Este jogo não oferece dinheiro real. Recompensas virtuais.</p>

  <script>
    const gameArea = document.getElementById('gameArea');
    const scoreEl = document.getElementById('score');
    const coinsEl = document.getElementById('coins');

    let score = 0;
    let coins = 0;
    let speed = 1500;

    function randomColor() {
      const colors = ['#ffeb3b', '#4caf50', '#03a9f4', '#ff5722', '#e91e63'];
      return colors[Math.floor(Math.random() * colors.length)];
    }

    function createCircle() {
      const circle = document.createElement('div');
      circle.className = 'circle';
      circle.style.background = randomColor();

      const size = Math.floor(Math.random() * 40) + 40;
      circle.style.width = size + 'px';
      circle.style.height = size + 'px';

      circle.style.left = Math.random() * (window.innerWidth - size) + 'px';
      circle.style.top = Math.random() * (gameArea.offsetHeight - size) + 'px';

      circle.onclick = () => {
        score += 10;
        coins += 1;
        scoreEl.innerText = 'Pontos: ' + score;
        coinsEl.innerText = 'Moedas: ' + coins + ' 🪙';
        circle.remove();
        speed = Math.max(400, speed - 20);
      };

      gameArea.appendChild(circle);

      setTimeout(() => {
        if (circle.parentNode) circle.remove();
      }, speed);
    }

    function startGame() {
      setInterval(createCircle, speed);
    }

    startGame();
  </script>
</body>
</html>


---

🚀 Próximos passos (eu posso ajudar)

Adicionar sons 🎵

Sistema de níveis

Loja virtual fictícia 🛒

Tela de início e fim

Preparar para anúncios (AdSense / outras redes)


👉 Diz-me: queres melhorar este jogo agora ou queres ajuda para divulgar e monetizar?
