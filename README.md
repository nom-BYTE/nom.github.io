# nom.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Happy Birthday Dad!</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Segoe UI', sans-serif;
      color: #333;
      scroll-behavior: smooth;
    }
    section {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 2rem;
      flex-direction: column;
      text-align: center;
    }
    .welcome {
      background: url('https://images.unsplash.com/photo-1608889175110-d6c5d442654c?auto=format&fit=crop&w=1650&q=80') no-repeat center center/cover;
      color: white;
    }
    .welcome h1 {
      font-size: 3rem;
      animation: bounceInDown 2s;
      text-shadow: 2px 2px 5px #000;
    }
    .card-section {
      background-color: #ffffff;
    }
    .card-section h2 {
      margin-bottom: 1rem;
    }
    .card {
      background: #fff;
      width: 300px;
      height: 200px;
      perspective: 1000px;
      cursor: pointer;
      margin: 2rem 0;
    }
    .card-inner {
      width: 100%;
      height: 100%;
      transition: transform 1s;
      transform-style: preserve-3d;
      position: relative;
    }
    .card-inner.flipped,
    .card:hover .card-inner {
      transform: rotateY(180deg);
    }
    .card-front, .card-back {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 15px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.3);
      font-size: 1.2rem;
    }
    .card-front {
      background: #ffd700;
    }
    .card-back {
      background: #ff6f61;
      color: white;
      transform: rotateY(180deg);
    }
    .message-section {
      background-color: #f0f8ff;
    }
    .message {
      background: rgba(255, 255, 255, 0.95);
      padding: 2rem;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.2);
      max-width: 800px;
      margin-top: 2rem;
      animation: fadeInUp 2s;
    }
    .quote-section {
      background-color: #ffecd2;
    }
    .quote {
      font-size: 1.5rem;
      color: #333;
      padding: 1rem;
    }
    .final-section {
      background: linear-gradient(to right, #ff758c, #ff7eb3);
      flex-direction: column;
    }
    .reveal-button {
      padding: 1rem 2rem;
      font-size: 1.2rem;
      border: none;
      background: #4CAF50;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      transition: background 0.3s;
      margin-top: 2rem;
    }
    .reveal-button:hover {
      background: #45a049;
    }
    .final-message {
      font-size: 2rem;
      margin-top: 2rem;
      color: white;
      display: none;
      font-weight: bold;
      animation: fadeIn 2s;
    }
    canvas#confetti-canvas {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      pointer-events: none;
      z-index: 1;
    }
    body > *:not(canvas) {
      position: relative;
      z-index: 2;
    }
  </style>
</head>
<body>
  <canvas id="confetti-canvas"></canvas>

  <section class="welcome">
    <h1 class="animate__animated animate__bounceInDown">🎉 Happy Birthday, Dad! 🎉</h1>
  </section>

  <section class="card-section">
    <h2 class="animate__animated animate__fadeInDown">🎁 Tap or Click This Card 🎁</h2>
    <div class="card" onclick="flipCard(this)">
      <div class="card-inner">
        <div class="card-front">Tap me 🎁</div>
        <div class="card-back">You're the best, Dad!</div>
      </div>
    </div>
  </section>

  <section class="message-section">
    <h2 class="animate__animated animate__fadeInUp">❤️ A Special Message ❤️</h2>
    <div class="message">
      <h2>Dear Dad,</h2>
      <p>Words can never fully capture how much you mean to me. Your hard work, your endless sacrifices, and your unshakable belief in me have shaped the person I am today. You are my superhero, my teacher, and my biggest inspiration.<br><br>
      On your special day, I want to say THANK YOU — for every sleepless night, every word of wisdom, and every moment you chose my smile over your comfort.<br><br>
      I love you beyond words, and I hope this day brings you as much joy as you’ve given me all my life.<br><br>
      — Your proud child, Nomaan</p>
    </div>
  </section>

  <section class="quote-section">
    <div class="quote">“A father is someone you look up to no matter how tall you grow.”</div>
  </section>

  <section class="final-section">
    <button class="reveal-button" onclick="showFinalMessage()">Tap for a surprise 🎇</button>
    <div class="final-message" id="finalMessage">
      HAPPY BIRTHDAY DAD ONCE AGAIN DAD YOU ARE OUR HERO — A LOT OF LOVE FROM NOMAAN, SUBHAAN, MUSKAN KHAN ❤️
    </div>
  </section>

  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>
  <script>
    const canvas = document.getElementById('confetti-canvas');
    const confettiSettings = { target: canvas };
    const confettiInstance = confetti.create(canvas, { resize: true });
    confettiInstance({ particleCount: 100, spread: 70, origin: { y: 0.6 } });

    function showFinalMessage() {
      const message = document.getElementById("finalMessage");
      message.style.display = "block";
      confettiInstance({ particleCount: 150, spread: 100, origin: { y: 0.4 } });
    }

    function flipCard(cardElement) {
      const inner = cardElement.querySelector('.card-inner');
      inner.classList.toggle('flipped');
    }
  </script>
</body>
</html>
