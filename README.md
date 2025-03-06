<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NCF Women's Celebration</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.4.0/dist/confetti.browser.min.js"></script>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background: linear-gradient(135deg, #ff6f61, #ffcc00, #ff9a9e);
            color: #fff;
            padding: 50px;
            margin: 0;
            overflow: hidden;
        }
        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            color: #ffffff;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: fadeIn 2s ease-in-out;
        }
        .logo {
            width: 150px;
            margin: 20px auto;
            animation: scaleLogo 2s ease-in-out infinite alternate;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes scaleLogo {
            0% { transform: scale(1); }
            100% { transform: scale(1.1); }
        }
        input {
            padding: 12px;
            font-size: 1rem;
            margin: 10px;
            border: none;
            border-radius: 5px;
            width: 80%;
            max-width: 300px;
            background: rgba(255, 255, 255, 0.8);
            color: #333;
            animation: slideIn 1s ease-in-out;
        }
        @keyframes slideIn {
            from { transform: translateY(-20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        button {
            padding: 12px 24px;
            font-size: 1rem;
            margin: 10px;
            border: none;
            border-radius: 25px;
            background: #ff3b2f;
            color: white;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            transition: background 0.3s ease;
            animation: fadeIn 2s ease-in-out;
        }
        button:hover {
            background: #ff1a1a;
            box-shadow: 0 6px 8px rgba(0, 0, 0, 0.3);
        }
        .invitation {
            display: none;
            margin-top: 30px;
            font-size: 1.2rem;
            animation: fadeIn 1s ease-in-out;
        }
        .reveal {
            cursor: pointer;
            padding: 20px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            margin: 20px auto;
            width: 80%;
            max-width: 500px;
            color: #fff;
            font-weight: bold;
            transition: background 0.3s ease;
            animation: slideIn 1s ease-in-out;
        }
        .reveal:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        a {
            color: #ffdd57;
            text-decoration: none;
            font-weight: bold;
        }
        a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>NCF Women's Celebration 🎉</h1>
    <!-- Update the src attribute to point to your logo file -->
    <img src="ncf-logo.png" alt="NCF Logo" class="logo">
    <p>Enter your name to receive your invitation:</p>
    <input type="text" id="nameInput" placeholder="Your Name">
    <button onclick="startCelebration()">Start Celebration</button>

    <div id="invitation" class="invitation">
        <h2>🎉 Happy Women's Day, <span id="userName"></span>! 🎉</h2>
        <div id="timeReveal" class="reveal" onclick="revealTime()">
            👉 Click to Reveal Time
        </div>
        <div id="placeReveal" class="reveal" onclick="revealPlace()">
            👉 Click to Reveal Place
        </div>
    </div>

    <script>
        function startCelebration() {
            const name = document.getElementById('nameInput').value;
            if (name) {
                // Show invitation
                document.getElementById('invitation').style.display = 'block';
                document.getElementById('userName').textContent = name;

                // Trigger confetti effect
                confetti({
                    particleCount: 300,
                    spread: 100,
                    origin: { y: 0.6 }
                });

                // Add more cracker effects
                setTimeout(() => confetti({ particleCount: 200, spread: 70, origin: { x: 0.3, y: 0.6 } }), 500);
                setTimeout(() => confetti({ particleCount: 200, spread: 70, origin: { x: 0.7, y: 0.6 } }), 1000);
                setTimeout(() => confetti({ particleCount: 200, spread: 70, origin: { x: 0.5, y: 0.6 } }), 1500);
            } else {
                alert('Please enter your name!');
            }
        }

        function revealTime() {
            document.getElementById('timeReveal').innerHTML = `
                <strong>Time:</strong> March 8, 2024 at 6:00 PM
            `;
        }

        function revealPlace() {
            document.getElementById('placeReveal').innerHTML = `
                <strong>Place:</strong> Online Event - <a href="https://meet.google.com/kqt-zzbu-dkw" target="_blank">Join Here</a>
            `;
        }
    </script>
</body>
</html>
