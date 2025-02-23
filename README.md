<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Wee Hieng 的脑子</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f0f0f0;
      margin: 0;
      padding: 0;
    }
    #brain {
      position: relative;
      width: 100%;
      height: 100vh;
      background-image: url('./brain-image.jpg.jpg'); /* 脑子的图片 */
      background-size: cover;
      background-position: center;
      cursor: pointer;
    }
    .message {
      position: absolute;
      top: 20px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 24px;
      color: #333;
      background-color: rgba(255, 255, 255, 0.8);
      padding: 10px 20px;
      border-radius: 10px;
    }
    .image-popup {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: white;
      padding: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
      cursor: pointer;
    }
    .image-popup img {
      max-width: 200px;
      max-height: 200px;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <h1>Wee Hieng 的脑子</h1>
  <div id="brain">
    <!-- 点击区域 -->
    <div id="click-area" style="position: absolute; top: 10%; left: 25%; width: 50%; height: 65%;"></div>
  </div>
  <div class="message" id="message"></div>

  <!-- 图片弹窗 -->
  <div id="image-popup" class="image-popup">
    <img id="popup-image" src="" alt="Popup Image">
    <p id="popup-text"></p>
  </div>

  <script>
    const messageElement = document.getElementById('message');
    const brain = document.getElementById('brain');
    const clickArea = document.getElementById('click-area');
    const imagePopup = document.getElementById('image-popup');
    const popupImage = document.getElementById('popup-image');
    const popupText = document.getElementById('popup-text');

    // 随机文字和图片
    const texts = [
      'DOMO', 'KELLY', 'JIACHEE', '月>', '暴躁的蔡文姬', '暴躁的瑶',
      '我好喜欢你', '你真的好漂亮', '别天天不开心了'
    ];
    const images = [
      './caiwenji.jpg.jpeg',
      './domo.jpg.jpeg',
      './jiachee.jpg.jpeg',
      './kelly.jpg.jpeg',
      './moon.jpg.jpeg',
      './yao.jpg.jpeg',
      './k1.jpg.jpeg', // 新增照片
      './k2.jpg.jpeg', // 新增照片
      './k3.jpg.jpeg', // 新增照片
      './k4.jpg.jpeg', // 新增照片
      './k5.jpg.jpeg', // 新增照片
      './k6.jpg.jpeg', // 新增照片
      './k7.jpg.jpeg', // 新增照片
      './k8.jpeg',    // 新增照片
      './k9.jpeg'     // 新增照片
    ];

    // 随机选择一个文字和一张图片
    function getRandomItem(array) {
      return array[Math.floor(Math.random() * array.length)];
    }

    // 显示图片和文字
    function showPopup(text, image) {
      popupText.textContent = text;
      popupImage.src = image;
      imagePopup.style.display = 'block';

      // 3 秒后自动关闭
      setTimeout(() => {
        imagePopup.style.display = 'none';
      }, 3000);
    }

    // 点击中间区域
    clickArea.addEventListener('click', () => {
      const randomText = getRandomItem(texts);
      const randomImage = getRandomItem(images);
      showPopup(randomText, randomImage);
    });

    // 点击图片弹窗关闭
    imagePopup.addEventListener('click', () => {
      imagePopup.style.display = 'none';
    });
  </script>
</body>
</html>
