<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Maki-CB</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      min-height: 100vh;
      background: linear-gradient(135deg, #111827, #312e81);
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      overflow: hidden;
    }

    .container {
      width: 90%;
      max-width: 400px;
      text-align: center;
      animation: appear 1s ease;
    }

    .logo {
      font-size: 65px;
      margin-bottom: 15px;
      animation: float 2s infinite ease-in-out;
    }

    h1 {
      font-size: 35px;
      margin-bottom: 10px;
    }

    p {
      color: #d1d5db;
      margin-bottom: 30px;
    }

    button {
      width: 100%;
      padding: 16px;
      border: none;
      border-radius: 15px;
      font-size: 18px;
      font-weight: bold;
      cursor: pointer;
      margin-top: 10px;
      transition: 0.25s;
    }

    .cb {
      background: white;
      color: #312e81;
    }

    .cb:hover {
      transform: scale(1.04);
    }

    .about {
      background: rgba(255,255,255,0.12);
      color: white;
    }

    .chat {
      display: none;
      margin-top: 20px;
      background: rgba(255,255,255,0.1);
      padding: 20px;
      border-radius: 20px;
      backdrop-filter: blur(10px);
    }

    .message {
      background: white;
      color: #111827;
      padding: 12px;
      border-radius: 15px;
      margin-bottom: 15px;
      text-align: left;
    }

    .input {
      display: flex;
      gap: 8px;
    }

    input {
      flex: 1;
      padding: 13px;
      border: none;
      border-radius: 12px;
      outline: none;
    }

    .send {
      width: 70px;
      margin: 0;
      padding: 10px;
      background: white;
      color: #312e81;
    }

    @keyframes appear {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes float {
      0%, 100% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-10px);
      }
    }
  </style>
</head>

<body>

  <div class="container">

    <div class="logo">💬</div>

    <h1>Maki-CB</h1>
    <p>Welcome! Tara, maki-chat tayo.</p>

    <button class="cb" onclick="openChat()">
      💬 MAKI-CB
    </button>

    <button class="about" onclick="showAbout()">
      ℹ️ ABOUT
    </button>

    <div class="chat" id="chat">

      <div class="message">
        👋 Hello! Welcome sa CB!
      </div>

      <div class="input">
        <input id="msg" type="text" placeholder="Type your message...">
        <button class="send" onclick="sendMessage()">Send</button>
      </div>

    </div>

  </div>

  <script>
    function openChat() {
      document.getElementById("chat").style.display = "block";
    }

    function showAbout() {
      alert("Welcome sa Maki-CB website! 💬");
    }

    function sendMessage() {
      const input = document.getElementById("msg");
      const text = input.value.trim();

      if (text === "") return;

      const chat = document.getElementById("chat");

      const message = document.createElement("div");
      message.className = "message";
      message.textContent = "You: " + text;

      chat.insertBefore(message, chat.querySelector(".input"));

      input.value = "";
    }
  </script>

</body>
</html>
