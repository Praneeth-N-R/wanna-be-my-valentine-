<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 Be My Valentine? 💖</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');
        
        body {
            background-color: #C8A2C8;
            color: red;
            text-align: center;
            font-family: 'Dancing Script', cursive;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            position: relative;
        }
        
        h1 {
            font-size: 3.5rem;
            text-shadow: 3px 3px 6px white;
            opacity: 1;
            font-weight: bold;
        }
        
        .button-container {
            margin-top: 30px;
            display: flex;
            gap: 20px;
        }
        
        .btn {
            font-size: 1.5rem;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            transition: 0.3s;
        }
        
        .yes {
            background-color: pink;
            color: red;
        }
        
        .no {
            background-color: white;
            color: red;
            position: absolute;
            transition: transform 0.3s ease-in-out;
        }
        
        .emoji-background, .flower-decoration {
            position: absolute;
            font-size: 2rem;
            opacity: 0.5;
            animation: float 5s infinite alternate;
        }
        
        .flower-decoration {
            font-size: 3rem;
            opacity: 0.7;
        }
        
        @keyframes float {
            0% { transform: translateY(0); }
            100% { transform: translateY(-20px); }
        }
    </style>
</head>
<body>
    <h1>💘 Will You Be My Valentine? 💘</h1>
    <div class="button-container">
        <button class="btn yes" onclick="showMessage()">💞 Yes 💞</button>
        <button class="btn no" onmouseover="moveButton()">💔 No 💔</button>
    </div>
    
    <audio id="music" autoplay loop>
        <source src="your-audio-file.mp3" type="audio/mpeg">
    </audio>
    
    <script>
        function moveButton() {
            const noButton = document.querySelector('.no');
            const x = Math.random() * (window.innerWidth - 150);
            const y = Math.random() * (window.innerHeight - 100);
            noButton.style.transform = `translate(${x}px, ${y}px)`;
        }

        function showMessage() {
            document.body.innerHTML = '<h1 style="display: flex; flex-direction: column; justify-content: center; align-items: center; height: 100vh; text-shadow: 3px 3px 6px white; font-size: 3.5rem; opacity: 1; font-weight: bold;">💖 Thank You for Being My Valentine! 💖<br><br>❤️ I Love You and You Are Very Special to Me! ❤️</h1>';
            addDecorations();
        }

        function addDecorations() {
            for (let i = 0; i < 30; i++) {
                let emoji = document.createElement('div');
                emoji.className = 'emoji-background';
                emoji.innerHTML = ['💖', '💕', '💘', '❤️', '💓', '💞'][Math.floor(Math.random() * 6)];
                emoji.style.left = Math.random() * window.innerWidth + 'px';
                emoji.style.top = Math.random() * window.innerHeight + 'px';
                document.body.appendChild(emoji);
            }
            
            for (let i = 0; i < 15; i++) {
                let flower = document.createElement('div');
                flower.className = 'flower-decoration';
                flower.innerHTML = '🌸';
                flower.style.left = Math.random() * window.innerWidth + 'px';
                flower.style.top = Math.random() * window.innerHeight + 'px';
                document.body.appendChild(flower);
            }
        }
        
        addDecorations();
    </script>
</body>
</html>
