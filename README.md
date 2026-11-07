<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>A Birthday Letter For You!</title>
  <style>
    * { box-sizing: border-box; }

    body {
      margin: 0;
      min-height: 100vh;
      overflow-x: hidden;
      background: #08090d;
      color: #fff;
      font-family: Georgia, "Times New Roman", serif;
    }

    /* Soft, moving fog */
    .fog {
      position: fixed;
      inset: -40%;
      z-index: -2;
      pointer-events: none;
      background:
        radial-gradient(ellipse at 20% 45%, #ffffff24 0%, transparent 38%),
        radial-gradient(ellipse at 75% 55%, #cbd1dc20 0%, transparent 42%),
        radial-gradient(ellipse at 50% 20%, #ffffff16 0%, transparent 35%);
      filter: blur(35px);
      animation: drift 24s ease-in-out infinite alternate;
    }

    .fog.second {
      opacity: 0.65;
      animation: drift 34s ease-in-out infinite alternate-reverse;
      transform: scale(1.2);
    }

    @keyframes drift {
      from { transform: translate(-5%, -2%) scale(1); }
      to   { transform: translate(6%, 4%) scale(1.15); }
    }

    /* Falling stars */
    .star {
      position: fixed;
      top: -30px;
      z-index: -1;
      color: white;
      pointer-events: none;
      text-shadow: 0 0 10px #fff, 0 0 20px #cbdcff;
      animation: fall linear forwards;
    }

    @keyframes fall {
      to {
        transform: translateY(110vh) rotate(240deg);
        opacity: 0.15;
      }
    }

    main {
      width: min(900px, calc(100% - 32px));
      margin: 0 auto;
      padding: 54px 0;
    }

    header { text-align: center; margin-bottom: 36px; }

    h1 {
      margin: 0 0 10px;
      font-size: clamp(2rem, 7vw, 3.5rem);
      text-shadow: 0 0 22px #ffffff45;
    }

    header p { color: #d3d5de; }

    .photos {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 18px;
      margin-bottom: 30px;
    }

    .photos img {
      display: block;
      width: 100%;
      height: 340px;
      object-fit: cover;
      border: 1px solid #ffffff50;
      border-radius: 16px;
      box-shadow: 0 10px 35px #0009;
    }

    .letter-card {
      padding: 24px;
      border: 1px solid #ffffff3d;
      border-radius: 18px;
      background: #11131acc;
      box-shadow: 0 12px 40px #0007;
      backdrop-filter: blur(8px);
    }

    label { display: block; margin-bottom: 12px; font-size: 1.2rem; }

    textarea {
      width: 100%;
      min-height: 210px;
      padding: 16px;
      resize: vertical;
      border: 1px solid #ffffff55;
      border-radius: 12px;
      outline: none;
      background: #08090dcc;
      color: white;
      font: 1rem/1.7 Georgia, "Times New Roman", serif;
    }

    textarea:focus { border-color: #d9e3ff; }

    button {
      margin-top: 14px;
      padding: 11px 18px;
      border: 1px solid #ffffff80;
      border-radius: 999px;
      background: #ffffff16;
      color: white;
      font: inherit;
      cursor: pointer;
    }

    button:hover { background: #ffffff2c; }

    #status { margin-left: 10px; color: #d3d5de; font-size: 0.9rem; }

    @media (max-width: 600px) {
      .photos { grid-template-columns: 1fr; }
      .photos img { height: auto; max-height: 440px; }
      main { padding-top: 36px; }
    }

    @media (prefers-reduced-motion: reduce) {
      .fog { animation: none; }
      .star { display: none; }
    }
  </style>
</head>
<body>
  <div class="fog"></div>
  <div class="fog second"></div>

  <main>
    <header>
      <h1>Happy 19th Birthday Mlady Dlovan ✨</h1>
      <p>November 8, 2026</p>
    </header>

    <section class="photos" aria-label="Birthday photos">
      <img src="photo1.jpg" alt="Birthday memory one" />
      <img src="photo2.jpg" alt="Birthday memory two" />
    </section>

   

    <section class="letter-card">
      <label for="letter"><strong>Your letter 💌</strong></label>
      <textarea id="letter" placeholder="Happy birfday mlady Dlovan! May Allah bless ya and keep u always happy and healthy all da time and grant u success in every single thing, like EVERY SINGLE THING. AMEEN ^^
I hope ur doing well, and i hope ur alr. U finally turned 19 🥹
I can't be any proud more than how im rn, u grew up 😭
I may not remember many things, but i still remember dat ur turning 19 today. I love u so much mlady ^^"></textarea>
      <button type="button" id="saveButton">Save letter on this device</button>
      <span id="status" aria-live="polite"></span>
    </section>
  </main>

  <script>
    // Keeps the letter in this browser on this device.
    const letter = document.getElementById("letter");
    const status = document.getElementById("status");

    letter.value = localStorage.getItem("birthdayLetter") || "";

    document.getElementById("saveButton").addEventListener("click", () => {
      localStorage.setItem("birthdayLetter", letter.value);
      status.textContent = "Saved on this device!";
    });

    // Creates the falling star/snow effect.
    function makeStar() {
      const star = document.createElement("span");
      star.className = "star";
      star.textContent = Math.random() > 0.5 ? "✦" : "✧";
      star.style.left = Math.random() * 100 + "vw";
      star.style.fontSize = (8 + Math.random() * 14) + "px";
      star.style.opacity = 0.4 + Math.random() * 0.6;
      star.style.animationDuration = (7 + Math.random() * 9) + "s";
      document.body.appendChild(star);

      setTimeout(() => star.remove(), 17000);
    }

    setInterval(makeStar, 300);
  </script>
</body>
</html>

<img width="347" height="603" alt="Screenshot 2026-11-07 234240" src="https://github.com/user-attachments/assets/86f1b644-9e77-474e-91dc-25fe2337a3be" /><img width="296" height="395" alt="Screenshot 2026-11-07 234249" src="https://github.com/user-attachments/assets/53e0cb64-b4ee-43db-a625-f3e55a28245c" />
