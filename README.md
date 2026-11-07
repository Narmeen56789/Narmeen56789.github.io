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
      display: grid;
      place-items: center;
      padding: 24px;
      color: #40233f;
      font-family: system-ui, sans-serif;
      text-align: center;
      background: linear-gradient(135deg, #ffe2ed, #e8ddff);
    }

    .card {
      width: min(100%, 520px);
      padding: 42px 28px;
      border: 1px solid #ffffffaa;
      border-radius: 28px;
      background: #ffffffd9;
      box-shadow: 0 18px 55px #673c6d26;
    }

    .cake { font-size: 4rem; }

    h1 {
      margin: 12px 0;
      color: #a23876;
      font-size: clamp(2rem, 8vw, 3.2rem);
    }

    .date {
      font-weight: 700;
      font-size: 1.15rem;
    }

    #countdown {
      margin-top: 24px;
      color: #713e83;
      font-size: 1.3rem;
      font-weight: 700;
    }

    .note {
      margin-top: 18px;
      color: #725d72;
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
    <p class="note">Make a wish — it’s your special day! ✨</p>
  </main>

  <script>
    // Uses the visitor's local time zone.
    const birthday = new Date(2026, 10, 8); // Months are zero-based: 10 = November
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
  </script>
</body>
</html>
