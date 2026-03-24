<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gülzar'a Özel ❤️</title>
    <style>
        body {
            background: #fffaf0;
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            text-align: center;
        }
        .main-img { width: 200px; border-radius: 20px; margin-bottom: 20px; }
        h1 { color: #e63946; }
        .btn-container { display: flex; gap: 20px; justify-content: center; margin-top: 20px; }
        button { padding: 15px 30px; font-size: 18px; border: none; border-radius: 10px; cursor: pointer; font-weight: bold; }
        #yes-btn { background: #2ecc71; color: white; }
        #no-btn { background: #e63946; color: white; position: relative; }
        #celebration { display: none; }
        .heart { position: fixed; color: #ff4d6d; animation: move 3s linear; }
        @keyframes move { from { top: 100vh; } to { top: -10vh; } }
    </style>
</head>
<body>
    <audio id="music" loop>
        <source src="https://codeskulptor-demos.commondatastorage.googleapis.com/descent/background%20music.mp3" type="audio/mpeg">
    </audio>

    <div id="question-screen">
        <img class="main-img" src="https://media.tenor.com/9O0Z-S3_U78AAAAM/cute-bear.gif">
        <h1>Gülzar beni seviyor musun?</h1>
        <div class="btn-container">
            <button id="yes-btn" onclick="celebrate()">EVET</button>
            <button id="no-btn" onmouseover="moveNo()">HAYIR</button>
        </div>
    </div>

    <div id="celebration">
        <h1 style="color: #e63946;">Bende seni seviyorum ❤️</h1>
        <img class="main-img" src="https://media.tenor.com/UInWnCjC_mIAAAAM/love-mochi.gif">
    </div>

    <script>
        function celebrate() {
            document.getElementById('question-screen').style.display = 'none';
            document.getElementById('celebration').style.display = 'block';
            document.getElementById('music').play();
            setInterval(() => {
                const heart = document.createElement('div');
                heart.innerHTML = '❤️';
                heart.className = 'heart';
                heart.style.left = Math.random() * 100 + 'vw';
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 3000);
            }, 300);
        }
        function moveNo() {
            const btn = document.getElementById('no-btn');
            btn.style.position = 'fixed';
            btn.style.left = Math.random() * 80 + 'vw';
            btn.style.top = Math.random() * 80 + 'vh';
        }
    </script>
</body>
</html>
