<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Anniversary Jerry 💙</title>
<style>
  body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #add8e6, #ffe4e1);
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: "Segoe UI", Arial, sans-serif;
    overflow: hidden;
    color: #ff69b4;
    text-align: center;
    padding: 20px;
    cursor: pointer;
  }

  .message {
    font-size: 1.8rem;
    line-height: 1.6;
    opacity: 0;
    transition: opacity 1s;
  }

  .hearts {
    position: absolute;
    width: 100%;
    height: 100%;
    pointer-events: none;
    overflow: hidden;
  }

  .heart {
    position: absolute;
    bottom: -50px;
    font-size: 2rem;
    animation: floatUp 6s linear infinite;
  }

  @keyframes floatUp {
    0% { transform: translateY(0) scale(1); opacity: 1; }
    100% { transform: translateY(-110vh) scale(0.5); opacity: 0; }
  }
</style>
</head>
<body>

<div class="message" id="msg">👉 Tap anywhere to start 💖</div>
<div class="hearts" id="hearts"></div>

<script>
  const messages = [
    "🙈 Arre Jerry... tum to bhool gayi na? (thoda taunt 😜)",
    "😌 Ab koi baat nahi... shayad festival ke chakkar me reh gaya hoga.",
    "💙 Happy Anniversary my dear Jerry 💙<br>I love you so much — not just for these 5 months or 5 years... but lifelong.",
    "💍 Main hamesha tumhare saath rahunga. Mujhe pata hai mera pyaar kabhi-kabhi filmy lagta hai, <br>lekin meri jaan... ye bilkul real hai.",
    "🌸 Main tumse kabhi nahi thakunga, na hi kabhi chhod kar jaaunga. <br>Bas tumhe pareshan karta rahunga aur tumhe jealous bhi banata rahunga. 😘",
    "🤗 Mujhe ye bolne me raat lag gayi... <br>par main chahata tha ye sab uss waqt bolun jab tum mere liye free ho.",
    "😭 I’m missing you so much... Jaldi milo mujhe. <br>Milte hi ek tight sa hug dena please. ❤️",
    "💖 I love you forever... and ever... and ever 💖"
  ];

  const msgBox = document.getElementById("msg");
  let index = -1;

  function showNextMessage() {
    if (index < messages.length - 1) {
      index++;
      msgBox.style.opacity = 0;
      setTimeout(() => {
        msgBox.innerHTML = messages[index];
        msgBox.style.opacity = 1;
      }, 500);
    }
  }

  document.body.addEventListener("click", showNextMessage);

  // Floating hearts
  const heartsContainer = document.getElementById("hearts");
  function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerText = "❤";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.color = Math.random() > 0.5 ? "deeppink" : "hotpink";
    heart.style.animationDuration = 4 + Math.random() * 3 + "s";
    heartsContainer.appendChild(heart);
    setTimeout(() => heart.remove(), 7000);
  }
  setInterval(createHeart, 600);
</script>

</body>
</html>
