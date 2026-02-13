# valentine
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>For You ❤️</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #ffdde1, #ee9ca7);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #333;
    }
    .card {
      background: #ffffffee;
      padding: 2.5rem;
      border-radius: 20px;
      max-width: 420px;
      width: 90%;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);
      animation: fadeIn 1.2s ease;
    }
    h1 {
      color: #e63946;
      margin-bottom: 1rem;
      font-size: 2rem;
    }
    p {
      font-size: 1.05rem;
      line-height: 1.6;
      margin-bottom: 1.5rem;
    }
    .heart {
      font-size: 3rem;
      animation: pulse 1.5s infinite;
      margin-bottom: 1rem;
    }
    .question {
      font-size: 1.3rem;
      font-weight: 600;
      margin-top: 1.2rem;
      color: #d62828;
    }
    .buttons {
      margin-top: 1.5rem;
      display: flex;
      justify-content: center;
      gap: 1rem;
    }
    button {
      padding: 0.7rem 1.4rem;
      border: none;
      border-radius: 30px;
      font-size: 1rem;
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }
    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 15px rgba(0,0,0,0.2);
    }
    .yes {
      background: #e63946;
      color: #fff;
    }
    .no {
      background: #f1f1f1;
      color: #333;
    }
    .hidden {
      display: none;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.15); }
      100% { transform: scale(1); }
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="heart">❤️</div>
    <h1>Hi Labiba</h1>
    <p id="message">
      Labiba,
      <br /><br />
      I know I once said I don’t really like these things.
      But some things matter because they matter to <em>you</em>.
      And you matter to me.
    </p>

    <div id="valentineSection" class="hidden">
      <div class="question">Will you be my Valentine?</div>
      <div class="buttons">
        <button class="yes" onclick="answerYes()">Yes</button>
        <button class="no" onmouseover="moveNo(this)" onclick="answerNo()">No</button>
      </div>
    </div>

    <p id="response" class="hidden"></p>
  </div>

  <script>
    // Show the question only on or after 15 February (local time)
    const today = new Date();
    const showDate = new Date(today.getFullYear(), 1, 15); // Month is 0-indexed: 1 = February

    if (today >= showDate) {
      document.getElementById('valentineSection').classList.remove('hidden');
    } else {
      document.getElementById('message').innerText =
        "There is something meaningful waiting for you on 15 February.";
    }

    function answerYes() {
      const r = document.getElementById('response');
      r.classList.remove('hidden');
      r.innerText = "Thank you for saying yes. This means a lot ❤️";
    }

    function answerNo() {
      const r = document.getElementById('response');
      r.classList.remove('hidden');
      r.innerText = "Okay okay 😅 I had to try. You still mean the world to me.";
    }

    function moveNo(btn) {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 120 - 60;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }
  </script>
</body>
</html>
