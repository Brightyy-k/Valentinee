<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Valentine 💘</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Comic Sans MS', cursive, sans-serif;
    }

    .card {
      background: white;
      padding: 40px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 25px 50px rgba(0,0,0,0.25);
      z-index: 2;
    }

    h1 {
      color: #ff4d6d;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.3em;
    }

    .hearts {
      font-size: 1.8em;
      margin-bottom: 10px;
      animation: float 2s infinite ease-in-out;
    }

    @keyframes float {
      0% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0); }
    }

    .buttons {
      margin-top: 35px;
      position: relative;
      height: 120px;
      width: 350px;
    }

    button {
      padding: 15px 35px;
      font-size: 1.1em;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      position: absolute;
      transition: transform 0.2s;
    }

    #yes {
      background: #ff4d6d;
      color: white;
      left: 20px;
    }

    #yes:hover {
      transform: scale(1.1);
    }

    #no {
      background: #ddd;
      color: #555;
      left: 200px;
    }

    .confetti {
      position: fixed;
      top: -10px;
      font-size: 20px;
      animation: fall linear forwards;
      z-index: 1;
    }

    @keyframes fall {
      to {
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="hearts">💖💘💝💞💗</div>
    <h1>Ruveyda Kocabiyik</h1>
    <p>Will you be my Valentine? 🥺🌹✨</p>

    <div class="buttons">
      <button id="yes" onclick="yesClicked()">Yes 💕😍</button>
      <button id="no">No 😶</button>
    </div>
  </div>

  <script>
    const noBtn = document.getElementById("no");

    noBtn.addEventListener("mouseenter", () => {
      const maxX = window.innerWidth - noBtn.offsetWidth;
      const maxY = window.innerHeight - noBtn.offsetHeight;

      const x = Math.random() * maxX;
      const y = Math.random() * maxY;

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
      noBtn.style.transform = "scale(0.7)";
    });

    function yesClicked() {
      document.body.innerHTML = `
        <div style="
          height:100vh;
          display:flex;
          align-items:center;
          justify-content:center;
          background:#ff4d6d;
          color:white;
          font-family:'Comic Sans MS', cursive;
          text-align:center;
          flex-direction:column;
        ">
          <h1>YAAAAAY 💖🥰🎉</h1>
          <p>Officially Valentine material 💘🌹</p>
        </div>
      `;
      launchConfetti();
    }

    function launchConfetti() {
      const emojis = ["💖","💘","🎉","🌹","💝","✨"];
      for (let i = 0; i < 120; i++) {
        const conf = document.createElement("div");
        conf.className = "confetti";
        conf.innerText = emojis[Math.floor(Math.random() * emojis.length)];
        conf.style.left = Math.random() * 100 + "vw";
        conf.style.animationDuration = 2 + Math.random() * 3 + "s";
        document.body.appendChild(conf);

        setTimeout(() => conf.remove(), 5000);
      }
    }
  </script>
</body>
</html>


