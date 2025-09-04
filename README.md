<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>GAME CENTER</title>
    <style>
        html, body {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background: #000;
            font-family: Arial, sans-serif;
        }

        iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        /* กลุ่มปุ่มลอยเลือกเกม */
        .menu-buttons {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 9999;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .menu-buttons button {
            padding: 10px 20px;
            background: rgba(255, 0, 0, 0.8);
            color: #fff;
            font-size: 16px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s, transform 0.2s;
        }

        .menu-buttons button:hover {
            background: rgba(255, 0, 0, 1);
            transform: scale(1.05);
        }
    </style>
</head>
<body>
    <iframe id="gameFrame"
        src="https://zv1y2i8p.play.gamezop.com/g/S14VrK8B" 
        allowfullscreen 
        allowtransparency="true" 
        seamless>
    </iframe>

    <div class="menu-buttons">
        <button onclick="loadGame('https://zv1y2i8p.play.gamezop.com/g/S14VrK8B')">เกม 1</button>
        <button onclick="loadGame('https://zv1y2i8p.play.gamezop.com/g/SkhljT2fdgb')">เกม 2</button>
        <button onclick="loadGame('https://zv1y2i8p.play.gamezop.com/g/S1fJk3Labc')">เกม 3</button>
        <button onclick="shareGame()">แชร์</button>
        <button onclick="exitGame()">ออก</button>
    </div>

    <script>
        const iframe = document.getElementById('gameFrame');

        function loadGame(url) {
            iframe.src = url; // โหลดเกมใหม่
        }

        function shareGame() {
            if (navigator.share) {
                navigator.share({
                    title: 'เล่นเกมสนุกๆ ที่ GAME CENTER',
                    url: window.location.href
                }).then(() => {
                    alert('แชร์เรียบร้อย!');
                }).catch((err) => console.log(err));
            } else {
                alert('ไม่รองรับการแชร์บนเบราว์เซอร์นี้');
            }
        }

        function exitGame() {
            window.location.href = "https://www.example.com"; // เปลี่ยนเป็นหน้าโฮม
        }
    </script>
</body>
</html>
