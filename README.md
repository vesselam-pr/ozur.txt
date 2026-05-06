# ozur.txt
<ozur html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beni Affet</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100vh;
            width: 100vw;
            overflow: hidden;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Arka plan çiçeği */
        .background-image {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('https://images.unsplash.com/photo-1559563458-527698bf5295?auto=format&fit=crop&q=80&w=1000'); /* Temsili çiçek, kendi görselini buraya ekleyebilirsin */
            background-size: cover;
            background-position: center;
            filter: brightness(0.7);
            z-index: 1;
        }

        .card {
            position: relative;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(15px);
            padding: 40px;
            border-radius: 25px;
            width: 85%;
            max-width: 350px;
            text-align: center;
            color: white;
            box-shadow: 0 15
            
