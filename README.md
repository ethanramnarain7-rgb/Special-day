
<!DOCTYPE html>
<html>
<head>
  <title>Be My Valentine ❤️</title>
  <style>
    body {
      background: linear-gradient(to right, #ff9a9e, #fad0c4);
      text-align: center;
      font-family: Arial, sans-serif;
      padding-top: 50px;
      overflow: hidden;
      transition: background 2s ease;
    }

    h1 {
      font-size: 2.5em;
      color: white;
    }

    p {
      font-size: 1.2em;
      max-width: 500px;
      margin: 20px auto;
      color: white;
    }

    button {
      padding: 15px 30px;
      font-size: 18px;
      border-radius: 25px;
      margin: 10px;
      border: none;
      cursor: pointer;
      transition: transform 0.2s;
    }

    .yes {
      background-color: #ff4d6d;
      color: white;
    }

    .no {
      background-color: #555;
      color: white;
    }

    .heart, .star {
      position: absolute;
      animation: floatUp 3s linear forwards;
    }

    @keyframes floatUp {
      0% { transform: translateY(0); opacity: 1; }
      100% { transform: translateY(-500px); opacity: 0; }
    }
  </style>
</head>

<body>

  <h1>Will you be my Valentine? 💖</h1>

  <p id="message">
    I really like you and I was hoping we could spend Valentine’s Day together ❤️
  </p>

  <button class="yes" onclick="yesClick()">Yes 💕</button>
  <button id="noBtn" class="no" onclick="noClick()">No 💔</button>

  <script>
    // YES button click
    function yesClick() {
      const message = document.getElementById("message");
      const yesBtn = document.querySelector(".yes");
      const noBtn = document.getElementById("noBtn");

      // Hide buttons
      yesBtn.style.display = "none";
      noBtn.style.display = "none";

      // Romantic message
      const fullText = 
`I know I’m away right now, but I want you to know something… 
From the moment I met you, my heart has been full of joy. 
Every thought of you makes me smile. 
I may not be with you right now, but you are always on my mind. 
Will you be my Valentine, today and every day? ❤️`;

      let index = 0;
      message.innerText = "";

      // Type effect
      const typing = setInterval(() => {
        message.innerText += fullText[index];
        index++;
        if(index === fullText.length) clearInterval(typing);
      }, 40);

      // Start hearts and stars
      setInterval(createHeart, 300);
      setInterval(createStar, 500);

      // Animate background
      let hue = 0;
      setInterval(() => {
        hue += 1;
        document.body.style.background = `linear-gradient(to right, hsl(${hue}, 90%, 85%), hsl(${(hue+30)%360}, 90%, 85%))`;
      }, 100);
    }

    // NO button shrinking
    let size = 18;
    function noClick() {
      size -= 3;
      const noBtn = document.getElementById("noBtn");
      noBtn.style.fontSize = size + "px";
      noBtn.style.padding = size + "px";
      if (size <= 6) noBtn.style.display = "none";
    }

    // Floating hearts
    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerText = "❤️";
      heart.style.left = Math.random() * window.innerWidth + "px";
      heart.style.fontSize = (10 + Math.random()*30) + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 3000);
    }

    // Floating sparkly stars
    function createStar() {
      const star = document.createElement("div");
      star.className = "star";
      star.innerText = "✨";
      star.style.left = Math.random() * window.innerWidth + "px";
      star.style.fontSize = (10 + Math.random()*20) + "px";
      document.body.appendChild(star);
      setTimeout(() => star.remove(), 3000);
    }
  </script>

</body>
</html>
# Special-day
