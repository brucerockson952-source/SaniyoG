<!DOCTYPE html>
<html>
<head>
  <title>For You 💖</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background-color: #1a0a10;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      font-family: Georgia, serif;
    }

    /* PASSWORD SCREEN */
    #lock-screen {
      text-align: center;
      color: white;
    }

    #lock-screen h2 {
      color: #f5b8d0;
      font-size: 1.8rem;
      margin-bottom: 10px;
    }

    #lock-screen p {
      color: #e07499;
      font-style: italic;
      margin-bottom: 30px;
    }

    #lock-screen input {
      background: rgba(255,255,255,0.08);
      border: 1px solid #e75480;
      border-radius: 10px;
      padding: 12px 20px;
      color: white;
      font-size: 1rem;
      text-align: center;
      outline: none;
      width: 220px;
      letter-spacing: 3px;
    }

    #lock-screen input::placeholder {
      color: rgba(255,255,255,0.3);
      letter-spacing: 1px;
    }

    #lock-screen button {
      display: block;
      margin: 15px auto 0;
      background: #e75480;
      color: white;
      border: none;
      border-radius: 10px;
      padding: 12px 30px;
      font-size: 1rem;
      cursor: pointer;
      font-family: Georgia, serif;
    }

    #lock-screen button:hover { background: #c94070; }

    #error-msg {
      color: #ff6b8a;
      margin-top: 12px;
      font-size: 0.9rem;
      display: none;
    }

    /* MAIN CONTENT */
    #main-content { display: none; }

    .card {
      background: rgba(255,255,255,0.08);
      border: 1px solid #e75480;
      border-radius: 20px;
      padding: 50px;
      max-width: 500px;
      text-align: center;
      color: white;
    }

    h1 { color: #f5b8d0; font-size: 2rem; margin-bottom: 10px; }
    .sub { color: #e07499; font-style: italic; margin-bottom: 30px; }
    .msg { line-height: 1.9; font-size: 1rem; color: #ffe0ec; }
    .msg span { color: #f5b8d0; font-weight: bold; }
    .bottom { color: #f9cfe0; font-size: 1.3rem; margin-top: 30px; }
    .sign { color: #e07499; font-size: 0.8rem; margin-top: 15px; letter-spacing: 2px; }

    .heart {
      font-size: 3rem;
      display: block;
      margin-bottom: 20px;
      animation: pulse 1.5s infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.2); }
    }
  </style>
</head>
<body>

  <!-- PASSWORD SCREEN -->
  <div id="lock-screen">
    <span style="font-size:3rem;">🔐</span>
    <h2>Enter the secret word</h2>
    <p>only one person knows this...</p>
    <input type="password" id="password-input" placeholder="type here..." />
    <button onclick="checkPassword()">Open 💖</button>
    <p id="error-msg">❌ Wrong word, try again!</p>
  </div>

  <!-- MAIN CONTENT -->
  <div id="main-content">
    <div class="card">
      <span class="heart">💖</span>
      <h1>For You</h1>
      <p class="sub">my favourite person in the world</p>
      <p class="msg">
        Every moment with you feels like <span>magic</span>.<br><br>
        You make ordinary days <span>extraordinary</span>
        just by being in them. Your smile is the thing
        I look forward to most, and your laugh might as well be my
        favourite sound in the universe.<br><br>
        You are <span>so deeply loved</span> —
        not just today, but every single day.
      </p>
      <p class="bottom">✨ Bruce ✨</p>
      <p class="sign">MADE WITH LOVE, JUST FOR YOU</p>
      <p class="sign">😏 Don't lemme laugh much, i might get hurt😂<p/>
    </div>
  </div>

  <script>
    // 👇 CHANGE THIS to your secret word
    const secretWord = "Rebel";

    function checkPassword() {
      const input = document.getElementById("password-input").value;
      if (input.toLowerCase() === secretWord.toLowerCase()) {
        document.getElementById("lock-screen").style.display = "none";
        document.getElementById("main-content").style.display = "block";
      } else {
        document.getElementById("error-msg").style.display = "block";
      }
    }

    // Allow pressing Enter key too
    document.getElementById("password-input").addEventListener("keypress", function(e) {
      if (e.key === "Enter") checkPassword();
    });
  </script>

</body>
</html>
