
<html lang="th">
<head>
<meta charset="UTF-8" />
<title>คิดถึงไหม?</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin-top: 50px;
    overflow: hidden;
    height: 100vh;
    position: relative;
    background-color: pink;
  }
  button {
    font-size: 24px;
    padding: 10px 20px;
    cursor: pointer;
    position: absolute;
  }
  #yes-button {
    left: 50%;
    top: 50%;
    transform: translate(-150%, -50%);
  }
  #no-button {
    left: 50%;
    top: 50%;
    transform: translate(50%, -50%);
    transition: opacity 0.5s ease;
  }
</style>
</head>
<body>

<h1 style="position:absolute;top:20px;width:100%;">คิดถึงไหม?</h1>
<button id="yes-button">YES</button>
<button id="no-button">NO</button>

<script>
  const yesButton = document.getElementById('yes-button');
  const noButton = document.getElementById('no-button');

  yesButton.addEventListener('click', () => {
    window.location.href = "love_end.html";
  });

  function moveNoButton() {
    const maxX = window.innerWidth - noButton.offsetWidth;
    const maxY = window.innerHeight - noButton.offsetHeight;
    const newX = Math.random() * maxX;
    const newY = Math.random() * maxY;
    noButton.style.left = newX + 'px';
    noButton.style.top = newY + 'px';
  }

  noButton.addEventListener('touchstart', (e) => {
    e.preventDefault();
    moveNoButton();
  });

  noButton.addEventListener('mouseover', moveNoButton);

  noButton.addEventListener('click', () => {
    noButton.textContent = 'YES';
    noButton.disabled = true;
    noButton.style.opacity = 0.5;
  });
</script>

</body>
</html>
