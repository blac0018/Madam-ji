<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Anu, My Love - Final Proposal</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      width: 100%;
      height: 100%;
      font-family: 'Segoe UI', sans-serif;
      background: url('https://images.unsplash.com/photo-1506748686214-e9df14d4d9d0?auto=format&fit=crop&w=1950&q=80') no-repeat center center fixed;
      background-size: cover;
      color: #fff;
      overflow: hidden;
    }
    .container {
      position: relative;
      width: 100%;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: rgba(0, 0, 0, 0.6);
      z-index: 2;
    }
    .slide {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 20px;
      max-width: 800px;
    }
    .slide.active {
      display: flex;
      animation: fadeIn 1.5s ease;
    }
    h1 {
      font-size: 2.5em;
      margin-bottom: 20px;
    }
    p {
      font-size: 1.4em;
    }
    .buttons {
      margin-top: 30px;
    }
    button {
      padding: 15px 30px;
      font-size: 1.2em;
      margin: 10px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      background: #e91e63;
      color: white;
      box-shadow: 0 0 10px #e91e63;
      transition: transform 0.3s ease;
    }
    button:hover {
      transform: scale(1.05);
      background: #ff70a6;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }
    .hearts, .roses {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 1;
    }
    .heart {
      position: absolute;
      width: 50px;
      height: 50px;
      background: red;
      transform: rotate(45deg);
      animation: fallBlur 12s linear infinite;
      opacity: 0.7;
      filter: blur(0.5px);
    }
    .heart::before, .heart::after {
      content: "";
      position: absolute;
      width: 50px;
      height: 50px;
      background: red;
      border-radius: 50%;
    }
    .heart::before { top: -25px; left: 0; }
    .heart::after { top: 0; left: -25px; }.rose {
  position: absolute;
  background: url('https://cdn-icons-png.flaticon.com/512/4481/4481024.png') no-repeat center center;
  background-size: contain;
  width: 40px;
  height: 40px;
  animation: dropDown 14s linear infinite;
  opacity: 0.95;
}

@keyframes fallBlur {
  0% { transform: translateY(-10vh) scale(1); opacity: 1; filter: blur(0); }
  100% { transform: translateY(100vh) scale(0.8); opacity: 0.4; filter: blur(2px); }
}

@keyframes dropDown {
  0% { transform: translateY(-10vh); opacity: 0; }
  100% { transform: translateY(100vh); opacity: 1; }
}

  </style>
</head>
<body>
  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/16/audio_3115f6bbce.mp3?filename=romantic-piano-ambient-110130.mp3" type="audio/mp3">
  </audio>  <div class="hearts" id="hearts"></div>
  <div class="roses" id="roses" style="display:none;"></div>  <div class="container">
    <div class="slide active">
      <h1>Hi Anu...</h1>
      <p>This isn't just a message — it's a moment from my heart.</p>
      <div class="buttons">
        <button onclick="nextSlide()">Next</button>
      </div>
    </div><div class="slide">
  <h1>From DIP Konar</h1>
  <p>I don’t know why I love you... but believe me, I really do.</p>
  <div class="buttons">
    <button onclick="nextSlide()">Next</button>
  </div>
</div>

<div class="slide">
  <h1>Our Memories</h1>
  <div class="buttons">
    <button onclick="nextSlide()">Next</button>
  </div>
</div>

<div class="slide">
  <h1>Will you marry me, Anu?</h1>
  <div class="buttons">
    <button onclick="yes()">YES</button>
    <button onclick="no()">NO</button>
  </div>
</div>

  </div>  <script>
    const slides = document.querySelectorAll('.slide');
    let currentSlide = 0;

    function nextSlide() {
      slides[currentSlide].classList.remove('active');
      currentSlide++;
      if (currentSlide < slides.length) {
        slides[currentSlide].classList.add('active');
      }
    }

    function yes() {
      document.querySelector('.container').innerHTML = '<div style="text-align:center;padding:50px;font-size:2em;color:#fff;z-index:3;position:relative;">Let\'s begin our forever, Anu.</div>';
      document.getElementById('roses').style.display = 'block';
      document.getElementById('hearts').style.display = 'none';
    }

    function no() {
      alert("Haha, no isn't an option!");
    }

    const heartContainer = document.getElementById('hearts');
    for (let i = 0; i < 20; i++) {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = 6 + Math.random() * 5 + 's';
      heartContainer.appendChild(heart);
    }

    const roseContainer = document.getElementById('roses');
    for (let i = 0; i < 15; i++) {
      const rose = document.createElement('div');
      rose.className = 'rose';
      rose.style.left = Math.random() * 100 + 'vw';
      rose.style.animationDuration = 6 + Math.random() * 5 + 's';
      roseContainer.appendChild(rose);
    }
  </script></body>
</html>
