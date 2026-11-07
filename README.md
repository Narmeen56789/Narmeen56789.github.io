<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy 19th Birthday!</title>

  <style>
    * { box-sizing: border-box; }

    body {
      min-height: 100vh;
      margin: 0;
      padding: 32px 18px;
      color: #fff0fb;
      font-family: system-ui, sans-serif;
      text-align: center;
      background:
        radial-gradient(ellipse at 18% 20%, #5b506177, transparent 38%),
        radial-gradient(ellipse at 82% 75%, #34243e99, transparent 42%),
        linear-gradient(135deg, #171619, #29262b 55%, #121114);
    }

    .card {
      width: min(100%, 650px);
      margin: 0 auto;
      padding: 36px 24px;
      border: 1px solid #ffffff25;
      border-radius: 28px;
      background: #211e24dd;
      box-shadow: 0 18px 55px #0008, 0 0 35px #bd70b522;
      backdrop-filter: blur(8px);
    }

    .cake { font-size: 4rem; }

    h1 {
      margin: 12px 0;
      color: #ffb8df;
      font-size: clamp(2rem, 8vw, 3.2rem);
      text-shadow: 0 0 22px #ef73bd55;
    }

    .date {
      color: #e7c7e4;
      font-weight: 700;
      font-size: 1.15rem;
    }

    #countdown {
      margin: 24px 0;
      color: #e4b7ff;
      font-size: 1.3rem;
      font-weight: 700;
    }

    .photos {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 12px;
      margin: 28px 0;
    }

    .photos img {
      width: 100%;
      height: 190px;
      object-fit: cover;
      border: 1px solid #ffffff35;
      border-radius: 16px;
    }

    button {
      padding: 12px 20px;
      border: 0;
      border-radius: 999px;
      color: #241523;
      background: #ffb8df;
      font: inherit;
      font-weight: 700;
      cursor: pointer;
    }

    button:hover { background: #ffd2eb; }

    .letter {
      margin-top: 20px;
      padding: 20px;
      border: 1px solid #ffffff20;
      border-radius: 18px;
      background: #ffffff0b;
      color: #eee1ed;
      line-height: 1.7;
      text-align: left;
      white-space: pre-line;
    }

    .note {
      margin-top: 22px;
      color: #c9becb;
    }
  </style>
</head>
<body>
  <main class="card">
    <div class="cake" aria-hidden="true">🎂</div>
    <h1>Happy 19th Birthday, Birthday Star!</h1>
    <p class="date">November 8, 2026</p>
    <p>Wishing you a day full of laughter, love, and cake! 🎉</p>

    <div id="countdown" aria-live="polite"></div>

    <h2>Some favorite memories 📸</h2>
    <div class="photos">
      <!-- Replace these filenames with your photo filenames. -->
      <img src="photo1.jpg" alt="A favorite memory" />
      <img src="photo2.jpg" alt="Another favorite memory" />
      <img src="photo3.jpg" alt="One more special memory" />
    </div>

    <button id="letterButton" type="button" aria-expanded="false">
      Open your birthday letter 💌
    </button>

    <div id="letter" class="letter" hidden>
Dear Birthday Star,

Happy 19th birthday! I hope your special day is filled with all the things that make you happiest. Thank you for being such a wonderful person and for making so many memories with me.

I hope this next year brings you lots of joy, laughter, and amazing adventures. You deserve the best!

With love,
Your Name
    </div>

    <p class="note">Make a wish — it’s your special day! ✨</p>
  </main>

  <script>
    const birthday = new Date(2026, 10, 8); // 10 means November
    const countdown = document.getElementById("countdown");

    function updateCountdown() {
      const remaining = birthday - new Date();

      if (remaining <= 0) {
        countdown.textContent = "🎉 It’s birthday time! 🎉";
        return;
      }

      const days = Math.floor(remaining / 86_400_000);
      const hours = Math.floor((remaining % 86_400_000) / 3_600_000);
      const minutes = Math.floor((remaining % 3_600_000) / 60_000);
      const seconds = Math.floor((remaining % 60_000) / 1_000);

      countdown.textContent =
        `${days}d ${hours}h ${minutes}m ${seconds}s to go!`;
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);

    const letterButton = document.getElementById("letterButton");
    const letter = document.getElementById("letter");

    letterButton.addEventListener("click", () => {
      const isOpening = letter.hidden;
      letter.hidden = !isOpening;
      letterButton.textContent = isOpening
        ? "Close your birthday letter 💌"
        : "Open your birthday letter 💌";
      letterButton.setAttribute("aria-expanded", isOpening);
    });
  </script>
</body>
</html>
