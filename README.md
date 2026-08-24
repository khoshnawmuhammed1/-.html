<!DOCTYPE html>
<html lang="ku">
<head>
  <meta charset="UTF-8">
  <title>تەسبیحاتی ڕۆژانە</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      margin-top: 50px;
      background: linear-gradient(to right, #fdfdfd, #3cb8c9);
      background-image: url('tasbih-bg.jpeg'); /* پشتەوەی قەڵەم‌نووسی */
      background-size: cover;
      background-position: center;
      color: #016958;
    }

    h1 {
      font-size: 38px;
      margin-bottom: 20px;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.4);
      background-color: rgba(255,255,255,0.6);
      display: inline-block;
      padding: 10px 25px;
      border-radius: 12px;
    }

    .section {
      margin: 30px auto;
      padding: 20px;
      background-color: rgba(255,255,255,0.8);
      border-radius: 20px;
      width: 85%;
      box-shadow: 0 0 20px rgba(0,0,0,0.25);
    }

    .counter {
      font-size: 50px;
      color: #00695c;
      border: 3px solid #004d40;
      border-radius: 50%;
      width: 120px;
      height: 120px;
      line-height: 120px;
      margin: 20px auto;
      background-color: #b2dfdb;
      box-shadow: 0 0 25px rgba(0,255,150,0.6);
    }

    button {
      font-size: 22px;
      padding: 12px 30px;
      background-color: #00796b;
      color: white;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      box-shadow: 0 5px 12px rgba(0,0,0,0.3);
      transition: transform 0.2s, background-color 0.3s;
    }

    button:hover {
      transform: scale(1.1);
      background-color: #004d40;
    }

    button:disabled {
      background-color: gray;
      cursor: not-allowed;
    }

    .message {
      margin-top: 20px;
      font-size: 22px;
      color: #00695c;
      font-weight: bold;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.3);
      background-color: rgba(255,255,255,0.7);
      display: inline-block;
      padding: 10px 20px;
      border-radius: 12px;
    }
  </style>
</head>
<body>
  <h1>تەسبیحاتی ڕۆژانە 🌙</h1>

  <!-- لا حول ولا قوة إلا بالله -->
  <div class="section">
    <h2>لا حول ولا قوة إلا بالله</h2>
    <div id="counter1" class="counter">0</div>
    <button id="btn1">کلیک بکە</button>
    <div id="msg1" class="message"></div>
  </div>

  <!-- استغفرالله -->
  <div class="section">
    <h2>استغفرالله</h2>
    <div id="counter2" class="counter">0</div>
    <button id="btn2">کلیک بکە</button>
    <div id="msg2" class="message"></div>
  </div>

  <!-- صلوات -->
  <div class="section">
    <h2>اللَّهُمَّ صَلِّ عَلَى مُحَمَّدٍ وَعَلَى آلِهِ...</h2>
    <div id="counter3" class="counter">0</div>
    <button id="btn3">کلیک بکە</button>
    <div id="msg3" class="message"></div>
  </div>

  <!-- رب لا تذرني فردا -->
  <div class="section">
    <h2>رَبِّ لَا تَذَرْنِي فَرْدًا وَأَنتَ خَيْرُ الْوَارِثِينَ</h2>
    <div id="counter4" class="counter">0</div>
    <button id="btn4">کلیک بکە</button>
    <div id="msg4" class="message"></div>
  </div>

  <script>
    function setupTasbih(btnId, counterId, msgId, maxCount, text) {
      let count = 0;
      const counter = document.getElementById(counterId);
      const button = document.getElementById(btnId);
      const message = document.getElementById(msgId);

      button.addEventListener("click", () => {
        if (count < maxCount) {
          count++;
          counter.textContent = count;
        }
        if (count === maxCount) {
          button.disabled = true;
          button.textContent = "تەواو بوو ✅";
          message.textContent = `🌸 ${text} تەواو بوو! ${maxCount} گەیشتی`;
        }
      });
    }

    // هەریەک بە ژمارەی 33
    setupTasbih("btn1", "counter1", "msg1", 1000, "لا حول ولا قوة إلا بالله");
    setupTasbih("btn2", "counter2", "msg2", 1000, "استغفرالله");
    setupTasbih("btn3", "counter3", "msg3", 1000, "اللَّهُمَّ صَلِّ عَلَى مُحَمَّدٍ...");
    setupTasbih("btn4", "counter4", "msg4", 5000, "رَبِّ لَا تَذَرْنِي فَرْدًا...");
  </script>
</body>
</html>
