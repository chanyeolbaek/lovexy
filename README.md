<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>可以和我和好吗？</title>
    <style>
        body {
            background-color: #ffc0cb; /* 粉色背景 */
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            color: #ffffff; /* 文字颜色改为白色 */
            display: flex; /* 使用Flexbox居中 */
            justify-content: center; /* 水平居中 */
            align-items: center; /* 垂直居中 */
            height: 100vh; /* 让主体内容垂直居中 */
        }
        .container {
            max-width: 800px; /* 放大主体部分 */
            width: 100%;
            padding: 40px;
            border-radius: 16px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            text-align: center;
            background-color: transparent; /* 去掉白色背景 */
        }
        img {
            width: 150px; /* 放大图片 */
            height: auto;
            margin-top: 20px;
        }
        h1 {
            color: #ffffff; /* 标题颜色改为白色 */
            font-size: 2em; /* 放大标题字体 */
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            padding: 15px 30px;
            margin: 0 10px;
            background-color: #ff69b4; /* 按钮颜色为粉色 */
            color: white; /* 按钮文字颜色为白色 */
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1em; /* 放大按钮字体 */
        }
        button:hover {
            background-color: #e06666; /* 按钮悬停颜色 */
        }
        .hidden {
            display: none; /* 默认隐藏新内容 */
        }
    </style>
</head>
<body>
    <div class="container">
        <img id="mainImage" src="images/heart.png" alt="爱心">
        <h1 id="mainText">可以和我和好吗？</h1>
        <div class="buttons">
            <button id="yes">可以</button>
            <button id="no">不要</button>
        </div>
        <!-- 新内容 -->
        <div class="hidden" id="newContent">
            <img src="images/hug.png" alt="拥抱">
            <h1>!!!喜欢你!! ( >_< )♡︎</h1>
        </div>
        <!-- “不要”后的震惊画面 -->
        <div class="hidden" id="shockedContent">
            <img src="images/shocked.png" alt="震惊">
            <h1 id="shockedText">？你认真的吗...</h1>
            <div class="buttons">
                <button id="yesAgain">可以</button>
                <button id="noAgain">不要</button>
            </div>
        </div>
        <!-- “不许选不要”画面 -->
        <div class="hidden" id="angryContent">
            <img id="angryImage" src="images/angry.png" alt="生气">
            <h1 id="angryText">不许选不要</h1>
            <div class="buttons">
                <button id="yesAgain2">可以</button>
                <button id="noAgain2">不要</button>
            </div>
        </div>
        <!-- “你只能和我和好”画面 -->
        <div class="hidden" id="cryingContent">
            <img src="images/crying.png" alt="哭泣">
            <h1>你只能和我和好</h1>
            <div class="buttons">
                <button id="finalYes">可以</button>
            </div>
        </div>
    </div>

    <script>
        // JavaScript代码保持不变
        const yesButton = document.getElementById('yes');
        const noButton = document.getElementById('no');
        const newContent = document.getElementById('newContent');
        const shockedContent = document.getElementById('shockedContent');
        const angryContent = document.getElementById('angryContent');
        const cryingContent = document.getElementById('cryingContent');
        const yesAgainButton = document.getElementById('yesAgain');
        const noAgainButton = document.getElementById('noAgain');
        const yesAgainButton2 = document.getElementById('yesAgain2');
        const noAgainButton2 = document.getElementById('noAgain2');
        const finalYesButton = document.getElementById('finalYes');

        yesButton.addEventListener('click', function() {
            document.getElementById('mainImage').style.display = 'none';
            document.getElementById('mainText').style.display = 'none';
            document.querySelector('.buttons').style.display = 'none';
            newContent.style.display = 'block';
        });

        noButton.addEventListener('click', function() {
            document.getElementById('mainImage').style.display = 'none';
            document.getElementById('mainText').style.display = 'none';
            document.querySelector('.buttons').style.display = 'none';
            shockedContent.style.display = 'block';
        });

        yesAgainButton.addEventListener('click', function() {
            shockedContent.style.display = 'none';
            angryContent.style.display = 'none';
            newContent.style.display = 'block';
        });

        noAgainButton.addEventListener('click', function() {
            shockedContent.style.display = 'none';
            angryContent.style.display = 'block';
        });

        yesAgainButton2.addEventListener('click', function() {
            angryContent.style.display = 'none';
            newContent.style.display = 'block';
        });

        noAgainButton2.addEventListener('click', function() {
            angryContent.style.display = 'none';
            cryingContent.style.display = 'block';
        });

        finalYesButton.addEventListener('click', function() {
            cryingContent.style.display = 'none';
            newContent.style.display = 'block';
        });
    </script>
</body>
</html>
