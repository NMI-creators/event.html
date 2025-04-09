<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>ウィークリーキャラクター人気投票</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      padding: 20px;
      background-color: #f4f4f4;
    }

    h1 {
      margin-bottom: 30px;
    }

    .vote-section {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
      margin-bottom: 50px;
    }

    .character-card {
      background-color: white;
      border: 2px solid #ccc;
      border-radius: 10px;
      width: 200px;
      padding: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    .character-card img {
      width: 100%;
      height: auto;
      border-radius: 5px;
    }

    .character-card button {
      margin-top: 10px;
      padding: 10px;
      width: 100%;
      font-size: 16px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    .character-card button:hover {
      background-color: #45a049;
    }

    #thankYouMessage {
      font-size: 18px;
      color: #008000;
      margin-bottom: 30px;
    }

    .result-section {
      margin-top: 40px;
    }

    .result-section h2 {
      margin-bottom: 20px;
    }

    .result-grid {
      display: flex;
      justify-content: center;
      gap: 30px;
      flex-wrap: wrap;
    }

    .result-card {
      width: 150px;
      background-color: #ffffff;
      border: 1px solid #bbb;
      border-radius: 10px;
      padding: 10px;
    }

    .result-card img {
      width: 100%;
      border-radius: 5px;
    }

    .result-card p {
      margin-top: 5px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h1>ウィークリーキャラクター<br>人気投票</h1>

  <div id="thankYouMessage"></div>

  <div class="vote-section">
    <div class="character-card">
      <img src="characterA.png" alt="キャラクターA">
      <button onclick="submitVote('キャラクターA')">キャラクターAに投票</button>
    </div>
    <div class="character-card">
      <img src="characterB.png" alt="キャラクターB">
      <button onclick="submitVote('キャラクターB')">キャラクターBに投票</button>
    </div>
    <div class="character-card">
      <img src="characterC.png" alt="キャラクターC">
      <button onclick="submitVote('キャラクターC')">キャラクターCに投票</button>
    </div>
    <div class="character-card">
      <img src="characterD.png" alt="キャラクターD">
      <button onclick="submitVote('キャラクターD')">キャラクターDに投票</button>
    </div>
  </div>

  <div class="result-section">
    <h2>先週の結果</h2>
    <div class="result-grid">
      <div class="result-card">
        <img src="IMG_6561.jpeg" alt="先週の1位：友澤">
        <p>1位：友澤</p>
      </div>
      <div class="result-card">
        <img src="IMG_6553.jpeg" alt="先週の2位：過去キヨ">
        <p>2位：過去キヨ</p>
      </div>
      <div class="result-card">
        <img src="IMG_6555.jpeg" alt="先週の3位：キヨさん">
        <p>3位：キヨさん</p>
      </div>
      <div class="result-card">
        <img src="IMG_6558.jpeg" alt="先週の4位：NAK-01ra">
        <p>4位：NAK-01ra</p>
      </div>
    </div>
  </div>

  <script>
    function submitVote(character) {
      const formURL = "https://docs.google.com/forms/d/e/あなたのフォームID/formResponse";
      const entryID = "entry.1234567890"; // Googleフォームの「選択肢」用のエントリーIDに置き換える

      const formData = new FormData();
      formData.append(entryID, character);

      fetch(formURL, {
        method: "POST",
        mode: "no-cors",
        body: formData
      });

      document.getElementById("thankYouMessage").textContent = "投票ありがとうございます！";
    }
  </script>

</body>
</html>
