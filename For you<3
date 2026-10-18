<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Open My Letter 💌</title>

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
  overflow: hidden;
  font-family: Arial, sans-serif;
  background: radial-gradient(circle, #41132f, #100817);
  color: white;
}

h1 {
  font-size: clamp(25px, 6vw, 40px);
  text-shadow: 0 0 20px #ff3caa;
}

.container {
  width: 100%;
  text-align: center;
  padding: 20px;
}

.envelope {
  position: relative;
  width: min(300px, 80vw);
  height: 190px;
  margin: 100px auto 45px;
  background: #e879b0;
  border-radius: 8px;
  perspective: 900px;
  cursor: pointer;
  filter: drop-shadow(0 15px 25px #0008);
}

.back {
  position: absolute;
  inset: 0;
  background: #d85c98;
  border-radius: 8px;
}

.letter {
  position: absolute;
  z-index: 2;
  left: 5%;
  top: 10%;
  width: 90%;
  height: 85%;
  padding: 20px 12px;
  background: #fff8ed;
  color: #8c3563;
  border-radius: 5px;
  transform: translateY(0);
  transition: transform 1s, height 1s;
  overflow: auto;
}

.letter h2 {
  font-family: Georgia, serif;
  margin-top: 0;
}

.letter textarea {
  width: 100%;
  height: 100px;
  border: none;
  outline: none;
  resize: none;
  background: transparent;
  color: #63304c;
  font-size: 15px;
  line-height: 1.5;
}

.front {
  position: absolute;
  inset: 0;
  z-index: 4;
  background: #e879b0;
  clip-path: polygon(0 0, 50% 55%, 100% 0,
                     100% 100%, 0 100%);
  border-radius: 8px;
}

.flap {
  position: absolute;
  z-index: 5;
  inset: 0 0 auto;
  height: 60%;
  background: #ffafd4;
  clip-path: polygon(0 0, 100% 0, 50% 100%);
  transform-origin: top;
  transition: transform 0.8s;
}

.heart {
  position: absolute;
  z-index: 6;
  top: 45%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 35px;
  transition: opacity .3s;
}

.envelope.open .flap {
  transform: rotateX(180deg);
}

.envelope.open .heart {
  opacity: 0;
}

.envelope.open .letter {
  transform: translateY(-140px);
  height: 230px;
  z-index: 3;
}

button {
  border: none;
  border-radius: 30px;
  padding: 12px 20px;
  margin: 5px;
  background: linear-gradient(45deg, #ff3c9e, #a92bff);
  color: white;
  font-weight: bold;
  cursor: pointer;
  box-shadow: 0 0 15px #ff3c9e66;
}

button:hover {
  filter: brightness(1.15);
}

#hearts {
  position: fixed;
  inset: 0;
  overflow: hidden;
  pointer-events: none;
  z-index: 10;
}

.floating-heart {
  position: absolute;
  bottom: -40px;
  animation: fly 4s linear forwards;
  filter: drop-shadow(0 0 8px #ff55bb);
}

@keyframes fly {
  0% {
    transform: translateY(0) rotate(0deg) scale(.7);
    opacity: 0;
  }
  15% { opacity: 1; }
  100% {
    transform: translateY(-110vh) rotate(360deg) scale(1.4);
    opacity: 0;
  }
}

@media (max-width: 400px) {
  .envelope {
    height: 165px;
  }
}
</style>
</head>

<body>
<div id="hearts"></div>

<div class="container">
  <p>✨ A LITTLE SURPRISE FOR YOU ✨</p>
  <h1>Gửi bạn một lá thư 💌</h1>
  <p>Nhấn vào phong bì để mở nhé!</p>

  <div class="envelope" id="envelope">
    <div class="back"></div>

    <div class="letter">
      <h2>Gửi người thương 💗</h2>
      <textarea id="message"
        placeholder="Viết lời nhắn của bạn ở đây..."></textarea>
    </div>

    <div class="front"></div>
    <div class="flap"></div>
    <div class="heart">❤️</div>
  </div>

  <button id="openBtn">💌 Mở thư</button>
  <button id="closeBtn">↩ Đóng thư</button>
</div>

<script>
const envelope = document.getElementById("envelope");
const openBtn = document.getElementById("openBtn");
const closeBtn = document.getElementById("closeBtn");
const hearts = document.getElementById("hearts");

let isOpen = false;

function openLetter() {
  if (isOpen) return;

  isOpen = true;
  envelope.classList.add("open");
  openBtn.textContent = "💖 Đã mở thư";

  createHearts(25);
}

function closeLetter() {
  isOpen = false;
  envelope.classList.remove("open");
  openBtn.textContent = "💌 Mở thư";
}

function createHearts(amount) {
  for (let i = 0; i < amount; i++) {
    const heart = document.createElement("span");

    heart.className = "floating-heart";
    heart.textContent = ["💗", "💖", "💕", "✨"][
      Math.floor(Math.random() * 4)
    ];

    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = 15 + Math.random() * 25 + "px";
    heart.style.animationDuration = 3 + Math.random() * 3 + "s";

    hearts.appendChild(heart);

    heart.addEventListener("animationend", () => {
      heart.remove();
    });
  }
}

envelope.addEventListener("click", openLetter);
openBtn.addEventListener("click", openLetter);
closeBtn.addEventListener("click", closeLetter);

// Tạo trái tim bay liên tục
setInterval(() => {
  if (isOpen) createHearts(2);
}, 1000);
</script>
</body>
</html>
