<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sana Bir Mesajım Var...</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body, html {
            height: 100vh; width: 100vw;
            overflow: hidden;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #000;
            display: flex; justify-content: center; align-items: center;
        }

        /* Dinamik Arka Plan */
        .bg {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-image: url('https://images.unsplash.com/photo-1518199266791-739d6ffc8ec1?auto=format&fit=crop&q=80&w=1200');
            background-size: cover; background-position: center;
            filter: brightness(0.4); z-index: 1;
            transition: 1s ease;
        }

        /* Cam Kart */
        .card {
            position: relative; z-index: 10;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            padding: 40px; border-radius: 30px;
            width: 90%; max-width: 400px;
            text-align: center; color: white;
            border: 1px solid rgba(255, 255, 255, 0.15);
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
            transition: 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .heart {
            font-size: 4rem; color: #ff4d6d;
            margin-bottom: 20px; animation: pulse 1.2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); text-shadow: 0 0 20px #ff4d6d; }
            100% { transform: scale(1); }
        }

        h1 { font-size: 2rem; color: #ffb7c5; margin-bottom: 15px; }
        p { font-size: 1.1rem; line-height: 1.6; margin-bottom: 25px; opacity: 0.9; }

        .btn {
            background: linear-gradient(45deg, #ff4d6d, #ff8fa3);
            color: white; border: none; padding: 15px 35px;
            border-radius: 50px; font-weight: bold; cursor: pointer;
            font-size: 1.1rem; transition: 0.3s;
            box-shadow: 0 10px 20px rgba(255, 77, 109, 0.3);
        }

        .btn:hover { transform: scale(1.05); background: #ff4d6d; }

        /* Başarı Ekranı (Gizli) */
        #success-content { display: none; }
        
        .floating-heart {
            position: absolute; color: #ff4d6d; pointer-events: none;
            z-index: 5; animation: fly 4s linear infinite;
        }

        @keyframes fly {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <div class="bg" id="bg"></div>

    <div class="card" id="main-card">
        <div class="heart">❤️</div>
        <div id="initial-content">
            <h1>Beni Affet...</h1>
            <p>Seni kırdığım her an için kalbim bin parçaya bölünüyor. Bizim hikayemiz burada bitmemeli. Seni her şeyden çok seviyorum.</p>
            <button class="btn" onclick="accept()">Seni Seviyorum, Affet...</button>
        </div>

        <div id="success-content">
            <h1>Seni Çok Seviyorum! ✨</h1>
            <p>Beni affettiğin için teşekkür ederim. Dünyanın en mutlu insanı şu an benim. ❤️</p>
            <div style="font-size: 3rem;">🥰🌹💍</div>
        </div>
    </div>

    <script>
        function accept() {
            // Kartı değiştir
            document.getElementById('initial-content').style.display = 'none';
            document.getElementById('success-content').style.display = 'block';
            document.getElementById('bg').style.filter = 'brightness(0.7) sepia(0.3)';
            
            // Konfeti kalpler yağdır
            for(let i=0; i<50; i++) {
                setTimeout(createHeart, i * 100);
            }
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'floating-heart';
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = '100vh';
            heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
            heart.style.opacity = Math.random();
            document.body.appendChild(heart);
            
            setTimeout(() => heart.remove(), 4000);
        }
    </script>
</body>
</html>
