<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>個人網站</title>
  <style>
    /* 全局樣式 */
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      text-align: center;
    }

    /* 個人首頁樣式 */
    body.index {
      background-color: #fff8dc; /* 淺黃色背景 */
    }

    .info .id, .info .name {
      color: #6b4226; /* 咖啡色文字 */
      background-color: #d2b48c; /* 淺棕色背景 */
      border: 2px solid #6b4226; /* 咖啡色框線 */
      border-radius: 6px; /* 圓角 */
      margin: 10px;
      padding: 10px;
      display: inline-block;
    }

    .photo img {
      width: 400px;
      height: 300px;
      border: 3px solid green; /* 綠色框線 */
      border-radius: 10px; /* 圓角 */
    }

    .button {
      display: inline-block;
      margin: 20px auto;
      padding: 10px 20px;
      background-color: #4CAF50;
      color: white;
      text-decoration: none;
      border-radius: 5px;
      font-size: 16px;
    }

    /* 個人收藏頁面樣式 */
    body.collect {
      background-color: #ffc0cb; /* 粉紅色背景 */
    }

    .image-container img {
      width: 400px;
      height: 300px;
      border: 2px solid blue; /* 藍色框線 */
      transition: all 1s; /* 漸變效果 */
    }

    .image-container img:hover {
      width: 450px;
      height: 300px;
    }

    .buttons button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      border: none;
      background-color: #4CAF50;
      color: white;
      border-radius: 5px;
    }
  </style>
</head>
<body class="index">
  <!-- 頁面切換按鈕 -->
  <div class="top-link">
    <a href="#collect" class="button" onclick="showPage('collect')">個人收藏</a>
  </div>

  <!-- 個人首頁內容 -->
  <div id="home" class="info">
    <div class="id">學號：41218107</div>
    <div class="name">姓名：鍾孟儒</div>
    <div class="photo">
      <img src="../Downloads/20240514_112328.jpg" alt="個人相片">
    </div>
    <div class="external-link">
      <a href="https://k0435.github.io/invest1125/" target="_blank" class="button">理財WebAPP</a>
    </div>
  </div>

  <!-- 個人收藏內容 -->
  <div id="collect" style="display: none;">
    <div class="image-container">
      <img id="collect-image" src="images/collect1.jpg" alt="收藏物品">
    </div>
    <div class="buttons">
      <button onclick="previousImage()">上一項收藏</button>
      <button onclick="nextImage()">下一項收藏</button>
    </div>
    <a href="#home" class="button" onclick="showPage('home')">返回首頁</a>
  </div>

  <script>
    // 切換頁面
    function showPage(page) {
      document.querySelectorAll('body > div').forEach(div => div.style.display = 'none');
      document.getElementById(page).style.display = 'block';
      document.body.className = page;
    }

    // 收藏圖片切換
    const images = ["images/collect1.jpg", "images/collect2.jpg", "images/collect3.jpg"];
    let currentIndex = 0;

    function previousImage() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      document.getElementById("collect-image").src = images[currentIndex];
    }

    function nextImage() {
      currentIndex = (currentIndex + 1) % images.length;
      document.getElementById("collect-image").src = images[currentIndex];
    }
  </script>
</body>
</html>
