# happy-new-year
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy New Year 2025</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: black;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .container {
            position: relative;
        }
        h1 {
            font-size: 50px;
            margin-bottom: 20px;
        }
        #countdown {
            font-size: 30px;
            margin-bottom: 20px;
        }
        .firework {
            position: absolute;
            width: 5px;
            height: 5px;
            background: yellow;
            border-radius: 50%;
            animation: explode 1.5s ease-out infinite;
        }
        @keyframes explode {
            0% { transform: scale(1); opacity: 1; }
            100% { transform: scale(10); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Happy New Year 2025! 🎉</h1>
        <div id="countdown"></div>
    </div>
    <script>
        function updateCountdown() {
            const now = new Date();
            const newYear = new Date('January 1, 2025 00:00:00');
            const diff = newYear - now;
            if (diff <= 0) {
                document.getElementById('countdown').innerHTML = "It's 2025!";
                return;
            }
            let days = Math.floor(diff / (1000 * 60 * 60 * 24));
            let hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            let minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            let seconds = Math.floor((diff % (1000 * 60)) / 1000);
            document.getElementById('countdown').innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
        }
        setInterval(updateCountdown, 1000);
        
        function createFirework() {
            const firework = document.createElement('div');
            firework.classList.add('firework');
            document.body.appendChild(firework);
            firework.style.left = Math.random() * window.innerWidth + 'px';
            firework.style.top = Math.random() * window.innerHeight + 'px';
            setTimeout(() => firework.remove(), 1500);
        }
        setInterval(createFirework, 300);
    </script>
</body>
</html>
