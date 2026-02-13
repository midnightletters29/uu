 <!DOCTYPE html>
 <html lang="en">
 <head>
-  <meta charset="UTF-8">
-  <title>Valentine Envelope 💖</title>
+  <meta charset="UTF-8" />
+  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
+  <title>Valentine Surprise 💖</title>
   <style>
+    :root {
+      --pink-bg: #ffe8f0;
+      --pink-main: #ff4f86;
+      --pink-dark: #d9336f;
+      --card: #fff;
+      --text: #4d1130;
+    }
+
+    * {
+      box-sizing: border-box;
+    }
+
     body {
-      background: #ffe6e6;
-      display: flex;
-      justify-content: center;
-      align-items: center;
-      height: 100vh;
-      font-family: Arial, sans-serif;
+      margin: 0;
+      min-height: 100vh;
+      font-family: "Segoe UI", Arial, sans-serif;
+      background: radial-gradient(circle at top, #ffd8e8, #ffeef5 50%, #fff8fb);
+      color: var(--text);
+      display: grid;
+      place-items: center;
+      overflow-x: hidden;
+      padding: 20px;
+    }
+
+    .panel {
+      width: min(820px, 100%);
+      background: rgba(255, 255, 255, 0.94);
+      border: 2px solid #ffc4d8;
+      border-radius: 18px;
+      box-shadow: 0 16px 40px rgba(217, 51, 111, 0.18);
+      padding: 28px;
+    }
+
+    h1,
+    h2 {
+      margin-top: 0;
+      text-align: center;
+      color: var(--pink-dark);
+    }
+
+    p {
+      line-height: 1.5;
+    }
+
+    .hidden {
+      display: none !important;
+    }
+
+    .center {
+      text-align: center;
+    }
+
+    .passcode-box {
+      max-width: 420px;
+      margin: 0 auto;
+    }
+
+    .code-input {
+      width: 100%;
+      font-size: 1.35rem;
+      padding: 12px 16px;
+      border-radius: 12px;
+      border: 2px solid #ffabc6;
+      outline: none;
+      text-align: center;
+      letter-spacing: 5px;
+      margin: 14px 0;
+    }
+
+    .code-input:focus {
+      border-color: var(--pink-main);
+      box-shadow: 0 0 0 4px rgba(255, 79, 134, 0.15);
+    }
+
+    button {
+      background: linear-gradient(135deg, #ff5f92, #ff3577);
+      color: #fff;
+      border: 0;
+      border-radius: 999px;
+      font-size: 1rem;
+      padding: 11px 20px;
+      cursor: pointer;
+      transition: transform 0.15s ease, box-shadow 0.2s ease;
+      box-shadow: 0 8px 18px rgba(255, 53, 119, 0.26);
+    }
+
+    button:hover {
+      transform: translateY(-2px);
+    }
+
+    .error-msg {
+      min-height: 22px;
+      color: #d1003f;
+      font-weight: 700;
+      text-align: center;
+      margin: 8px 0;
+    }
+
+    .envelope-stage {
+      display: grid;
+      place-items: center;
+      gap: 16px;
     }
 
     .envelope {
-      width: 300px;
-      height: 200px;
-      background: #ff4d6d;
       position: relative;
-      border-radius: 5px;
+      width: min(420px, 88vw);
+      height: 270px;
       cursor: pointer;
-      perspective: 1000px;
+      user-select: none;
+      margin-top: 6px;
     }
 
-    .flap {
+    .envelope-base {
+      position: absolute;
+      inset: 74px 0 0;
+      background: #ff5f92;
+      border-radius: 0 0 12px 12px;
+      box-shadow: 0 14px 28px rgba(217, 51, 111, 0.2);
+      overflow: hidden;
+    }
+
+    .envelope-base::before,
+    .envelope-base::after {
+      content: "";
+      position: absolute;
       width: 0;
       height: 0;
-      border-left: 150px solid transparent;
-      border-right: 150px solid transparent;
-      border-bottom: 100px solid #ff1a4d;
+      border-style: solid;
+      top: 0;
+    }
+
+    .envelope-base::before {
+      border-width: 98px 0 98px 205px;
+      border-color: transparent transparent transparent #ff4f86;
+      left: 0;
+    }
+
+    .envelope-base::after {
+      border-width: 98px 205px 98px 0;
+      border-color: transparent #ff4f86 transparent transparent;
+      right: 0;
+    }
+
+    .flap {
       position: absolute;
-      top: -100px;
+      top: 0;
       left: 0;
-      transform-origin: top;
-      transition: transform 0.5s;
+      width: 0;
+      height: 0;
+      border-left: 210px solid transparent;
+      border-right: 210px solid transparent;
+      border-top: 128px solid #ff2f74;
+      transform-origin: top center;
+      transition: transform 0.75s ease;
+      z-index: 3;
+      filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
     }
 
     .letter {
-      width: 260px;
-      height: 160px;
-      background: #fff0f5;
       position: absolute;
-      top: 20px;
-      left: 20px;
-      display: flex;
-      justify-content: center;
-      align-items: center;
-      font-size: 18px;
-      color: #ff1a4d;
-      padding: 10px;
-      border-radius: 5px;
-      opacity: 0;
-      transition: opacity 0.5s;
+      left: 50%;
+      top: 92px;
+      transform: translateX(-50%) translateY(0);
+      width: 85%;
+      background: #fff8fc;
+      border: 2px solid #ffc2d8;
+      border-radius: 12px;
+      padding: 16px;
+      box-shadow: 0 10px 18px rgba(0, 0, 0, 0.12);
+      transition: transform 0.7s ease;
+      z-index: 2;
+      text-align: center;
     }
 
     .envelope.open .flap {
       transform: rotateX(180deg);
     }
 
     .envelope.open .letter {
-      opacity: 1;
+      transform: translateX(-50%) translateY(-58px);
+    }
+
+    .note {
+      font-size: 0.94rem;
+      text-align: center;
+      color: #7a2b4c;
+    }
+
+    .surprise {
+      text-align: center;
+      position: relative;
+      overflow: hidden;
+    }
+
+    .celebrate {
+      font-size: clamp(2.3rem, 8vw, 4rem);
+      letter-spacing: 5px;
+      margin: 10px 0 2px;
+      animation: pulse 1.5s infinite;
+    }
+
+    .flowers {
+      font-size: clamp(1.7rem, 5vw, 2.6rem);
+      margin-bottom: 8px;
+    }
+
+    .spotify-card {
+      max-width: 500px;
+      margin: 18px auto 0;
+      background: #111;
+      color: #fff;
+      border-radius: 16px;
+      display: flex;
+      gap: 14px;
+      padding: 14px;
+      text-align: left;
+      align-items: center;
+      border: 1px solid #222;
+      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
+    }
+
+    .album-art {
+      width: 86px;
+      height: 86px;
+      border-radius: 10px;
+      background: linear-gradient(145deg, #89f7fe, #66a6ff);
+      display: grid;
+      place-items: center;
+      font-size: 2.3rem;
+      flex-shrink: 0;
+    }
+
+    .spotify-meta small {
+      color: #9c9c9c;
+    }
+
+    .fake-progress {
+      height: 4px;
+      width: 100%;
+      background: #353535;
+      border-radius: 999px;
+      margin-top: 8px;
+      overflow: hidden;
+    }
+
+    .fake-progress span {
+      display: block;
+      width: 64%;
+      height: 100%;
+      background: #1db954;
+    }
+
+    .confetti {
+      position: absolute;
+      top: -10px;
+      width: 9px;
+      height: 16px;
+      border-radius: 3px;
+      opacity: 0.9;
+      animation: fall linear forwards;
+    }
+
+    @keyframes pulse {
+      0%,
+      100% {
+        transform: scale(1);
+      }
+      50% {
+        transform: scale(1.06);
+      }
+    }
+
+    @keyframes fall {
+      to {
+        transform: translateY(430px) rotate(420deg);
+        opacity: 0;
+      }
     }
   </style>
 </head>
 <body>
+  <section id="lock-screen" class="panel">
+    <div class="passcode-box">
+      <h1>💘 Valentine Access 💘</h1>
+      <p class="center">Enter the passcode to unlock your surprise.</p>
+      <input id="passcode-input" class="code-input" type="password" inputmode="numeric" maxlength="4" placeholder="••••" aria-label="Passcode" />
+      <div class="center"><button id="unlock-btn" type="button">Unlock</button></div>
+      <p id="passcode-error" class="error-msg"></p>
+    </div>
+  </section>
+
+  <section id="envelope-screen" class="panel hidden">
+    <h2>Your Love Letter 💌</h2>
+    <div class="envelope-stage">
+      <div id="envelope" class="envelope" role="button" tabindex="0" aria-label="Open or close envelope">
+        <div class="flap"></div>
+        <div class="envelope-base"></div>
+        <article class="letter">
+          <p>
+            Hi love, <br />
+            You are my favorite hello and my hardest goodbye. Thank you for being my peace,
+            my laughter, and my best part of every day. Happy Valentine’s Day! 🌹
+          </p>
+          <p><strong>Tap the envelope to close it when you are done reading.</strong></p>
+        </article>
+      </div>
+      <p class="note">Tap once to open. Tap again to close and reveal your surprise 🎉</p>
+    </div>
+  </section>
+
+  <section id="surprise-screen" class="panel surprise hidden">
+    <h2>Surprise Time! 🎊</h2>
+    <div class="celebrate">PARTY MODE</div>
+    <p class="flowers">💐🌷🌹🌸🌺🌻✨</p>
+    <p>Because you deserve flowers, music, and all the love in the world.</p>
 
-  <div class="envelope" onclick="openEnvelope()">
-    <div class="flap"></div>
-    <div class="letter">
-      💌 Happy Valentine’s Day! You make my heart smile 💖
+    <div class="spotify-card" aria-label="Spotify style song card for Into You">
+      <div class="album-art">🎵</div>
+      <div class="spotify-meta">
+        <strong>Into You</strong><br />
+        <small>Ariana Grande · Dangerous Woman</small>
+        <div class="fake-progress"><span></span></div>
+      </div>
     </div>
-  </div>
+  </section>
 
   <script>
-    function openEnvelope() {
-      const envelope = document.querySelector('.envelope');
-      envelope.classList.toggle('open');
+    const PASSCODE = "0430";
+
+    const lockScreen = document.getElementById("lock-screen");
+    const envelopeScreen = document.getElementById("envelope-screen");
+    const surpriseScreen = document.getElementById("surprise-screen");
+    const passcodeInput = document.getElementById("passcode-input");
+    const unlockBtn = document.getElementById("unlock-btn");
+    const errorText = document.getElementById("passcode-error");
+    const envelope = document.getElementById("envelope");
+
+    let envelopeOpenedOnce = false;
+
+    function unlock() {
+      if (passcodeInput.value === PASSCODE) {
+        errorText.textContent = "";
+        lockScreen.classList.add("hidden");
+        envelopeScreen.classList.remove("hidden");
+      } else {
+        errorText.textContent = "Wrong passcode. Hint: 0430 💗";
+      }
     }
-  </script>
 
+    function launchConfetti() {
+      const colors = ["#ff2f74", "#ffc107", "#1db954", "#6a5cff", "#00c2ff"];
+
+      for (let i = 0; i < 70; i += 1) {
+        const dot = document.createElement("span");
+        dot.className = "confetti";
+        dot.style.left = `${Math.random() * 100}%`;
+        dot.style.background = colors[Math.floor(Math.random() * colors.length)];
+        dot.style.animationDuration = `${2.5 + Math.random() * 2}s`;
+        surpriseScreen.appendChild(dot);
+
+        setTimeout(() => dot.remove(), 5000);
+      }
+    }
+
+    function showSurprise() {
+      envelopeScreen.classList.add("hidden");
+      surpriseScreen.classList.remove("hidden");
+      launchConfetti();
+    }
+
+    function toggleEnvelope() {
+      const isOpen = envelope.classList.toggle("open");
+
+      if (isOpen) {
+        envelopeOpenedOnce = true;
+      } else if (envelopeOpenedOnce) {
+        showSurprise();
+      }
+    }
+
+    unlockBtn.addEventListener("click", unlock);
+    passcodeInput.addEventListener("keydown", (event) => {
+      if (event.key === "Enter") {
+        unlock();
+      }
+    });
+
+    envelope.addEventListener("click", toggleEnvelope);
+    envelope.addEventListener("keydown", (event) => {
+      if (event.key === "Enter" || event.key === " ") {
+        event.preventDefault();
+        toggleEnvelope();
+      }
+    });
+  </script>
 </body>
 </html>
 
EOF
)
