# Valentine.1
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<title>Valentine 💖</title>

<!-- Google Font -->
<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@400;600&display=swap" rel="stylesheet">

<style>
  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
    height: 100vh;
    overflow: hidden;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(-45deg, #ff6ec4, #7873f5, #4facfe, #43e97b);
    background-size: 400% 400%;
    animation: gradientBG 10s ease infinite;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  @keyframes gradientBG {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  .container {
    text-align: center;
    color: white;
    position: relative;
  }

  h1 {
    font-family: 'Pacifico', cursive;
    font-size: 3.2rem;
    margin-bottom: 40px;
    text-shadow: 0 5px 15px rgba(0,0,0,0.3);
  }

  .buttons {
    position: relative;
    width: 400px;
    height: 220px;
    margin: auto;
  }

  button {
    border: none;
    border-radius: 50px;
    padding: 16px 36px;
    font-size: 1.3rem;
    cursor: pointer;
    position: absolute;
    transition: transform 0.3s ease, opacity 0.4s ease;
    box-shadow: 0 10px 25px rgba(0,0,0,0.25);
  }

  #yes {
    background: linear-gradient(135deg, #00f260, #0575e6);
    color: white;
    left: 50%;
    top: 40px;
    transform: translateX(-50%);
    z-index: 2;
  }

  #no {
    background: linear-gradient(135deg, #ff416c, #ff4b2b);
    color: white;
    left: 50%;
    top: 120px;
    transform: translateX(-50%);
    z-index: 1;
  }

  .yay {
    display: none;
    font-family: 'Pacifico', cursive;
    font-size: 4.5rem;
    margin-top: 20px;
    animation: pop 0.7s ease forwards;
  }

  .gif {
    display: none;
    margin-top: 25px;
  }

  @keyframes pop {
    0% { transform: scale(0); opacity: 0; }
    100% { transform: scale(1); opacity: 1; }
  }
</style>
</head>

<body>

<div class="container">
  <h1>Priya, will you be my Valentine? 💖</h1>

  <div class="buttons">
    <button id="yes">YES 💘</button>
    <button id="no">NO 😏</button>
  </div>

  <div class="yay">YAY 🎉🥰</div>

  <div class="gif">
    <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZjYxMmJjMjE2YjY2N2U0OTIwN2UxZGU0ZGY0ZDNhZmNhMzg2NSZjdD1n/xT9IgIc0lryrxvqVGM/giphy.gif" width="260">
  </div>
</div>

<script>
  const noBtn = document.getElementById("no");
  const yesBtn = document.getElementById("yes");
  const yay = document.querySelector(".yay");
  const gif = document.querySelector(".gif");

  let yesScale = 1;
  let opacity = 1;

  // Make NO dance endlessly
  function moveNo() {
    const x = Math.random() * (window.innerWidth - 150);
    const y = Math.random() * (window.innerHeight - 150);

    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
    noBtn.style.transform = `rotate(${Math.random() * 360}deg)`;
  }

  setInterval(moveNo, 600);

  noBtn.addEventListener("mouseover", () => {
    yesScale += 0.15;
    yesBtn.style.transform = `translateX(-50%) scale(${yesScale})`;

    opacity -= 0.08;
    noBtn.style.opacity = opacity;

    if (opacity <= 0) {
      noBtn.style.display = "none";
    }
  });

  // YES click celebration
  yesBtn.addEventListener("click", () => {
    noBtn.style.display = "none";
    yesBtn.style.display = "none";
    yay.style.display = "block";
    gif.style.display = "block";
  });
</script>

</body>
</html>
