# rose-day-for-her
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rose Day Surprise</title>
    <style>
        body {
            background-color: #ffdae9;
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }
        
        .card {
            background: white;
            padding: 25px;
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            text-align: center;
            width: 85%;
            max-width: 350px;
            animation: slideIn 0.5s ease-out;
        }
        
        .hidden {
            display: none;
        }
        
        img {
            width: 100%;
            border-radius: 15px;
            margin-bottom: 15px;
        }
        
        h1 {
            color: #d63384;
            font-size: 22px;
        }
        
        p {
            color: #555;
            font-size: 16px;
        }
        
        button {
            background: #ff4d79;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 30px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 15px;
        }
        
        .rose-box {
            font-size: 50px;
            margin: 20px 0;
        }
        
        .rose {
            cursor: pointer;
            display: inline-block;
            transition: 0.3s;
        }
        
        .rose:active {
            transform: scale(0.8);
        }
        
        #msg {
            height: 20px;
            font-weight: bold;
            margin-top: 10px;
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>

<body>

    <div id="screen1" class="card">
        <img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=500" alt="Rose">
        <h1>Happy Rose Day, Baby!</h1>
        <p>A special surprise is waiting for you...</p>
        <button onclick="showScreen(2)">Open Surprise</button>
    </div>

    <div id="screen2" class="card hidden">
        <h1>Pick a Rose 🌹</h1>
        <p>Find the hidden message inside one of these...</p>
        <div class="rose-box">
            <span class="rose" onclick="wrong()">🌹</span>
            <span class="rose" onclick="correct()">🌹</span>
            <span class="rose" onclick="wrong()">🌹</span>
        </div>
        <div id="msg"></div>
    </div>

    <div id="screen3" class="card hidden">
        <h1 style="font-size: 30px;">❤️</h1>
        <p><i>"Just like this rose, you make my life beautiful. Thank you for being mine."</i></p>
        <h2 style="color: #ff4d79;">I Love You!</h2>
        <button onclick="location.reload()">Replay</button>
    </div>

    <script>
        function showScreen(num) {
            document.querySelectorAll('.card').forEach(c => c.classList.add('hidden'));
            document.getElementById('screen' + num).classList.remove('hidden');
        }

        function wrong() {
            const msg = document.getElementById('msg');
            msg.innerText = "Try another one! 🥀";
            msg.style.color = "orange";
        }

        function correct() {
            const msg = document.getElementById('msg');
            msg.innerText = "Success! Opening... ❤️";
            msg.style.color = "green";
            setTimeout(() => showScreen(3), 1500);
        }
    </script>
</body>

</html>
