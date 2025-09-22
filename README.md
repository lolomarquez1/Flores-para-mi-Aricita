<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para mi Aricita</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #0d0d1a;
            color: white;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: flex-end;
            min-height: 100vh;
        }

        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: transparent;
            z-index: 1;
        }

        .star {
            position: absolute;
            background-color: white;
            border-radius: 50%;
            animation: twinkle linear infinite;
        }

        @keyframes twinkle {
            0%, 100% { transform: scale(0.5); opacity: 0; }
            50% { transform: scale(1); opacity: 1; }
        }

        .sunflower-container {
            position: absolute;
            bottom: -50px;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: space-around;
            z-index: 2;
        }

        .sunflower {
            width: 80px;
            height: 80px;
            background-image: url('https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Sunflower_from_Silesia2.jpg/1200px-Sunflower_from_Silesia2.jpg');
            background-size: cover;
            animation: float 10s ease-in-out infinite;
        }

        @keyframes float {
            0% { transform: translateY(0); }
            50% { transform: translateY(-50px); }
            100% { transform: translateY(0); }
        }

        .message {
            text-align: center;
            padding: 20px;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 10px;
            margin-bottom: 20px;
            z-index: 3;
            animation: fadeIn 2s forwards;
            font-size: 1.5rem;
            font-weight: bold;
            text-shadow: 2px 2px 5px rgba(255, 193, 7, 0.8);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <div class="stars"></div>
    <div class="sunflower-container">
        <div class="sunflower" style="animation-delay: 1s;"></div>
        <div class="sunflower" style="animation-delay: 3s;"></div>
        <div class="sunflower" style="animation-delay: 5s;"></div>
    </div>
    <div class="message">
        <p>te amo demasiado mi Aricita, lo eres todo para mí❤️</p>
    </div>

    <script>
        const starsContainer = document.querySelector('.stars');
        function createStar() {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            star.style.width = `${Math.random() * 3 + 1}px`;
            star.style.height = star.style.width;
            star.style.animationDelay = `${Math.random() * 5}s`;
            starsContainer.appendChild(star);
        }
        for (let i = 0; i < 100; i++) {
            createStar();
        }
    </script>
</body>
</html>
