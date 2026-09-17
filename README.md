# Birthday
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Aami ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1a001a, #4d0026, #1a001a);
            color: #fff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            overflow-x: hidden;
            padding: 20px;
        }

        .container {
            max-width: 600px;
            width: 100%;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 105, 180, 0.3);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(255, 0, 128, 0.2);
            z-index: 2;
        }

        h1 {
            font-size: 2.5rem;
            color: #ff65a3;
            margin-bottom: 15px;
            animation: fadeIn 2s ease-in-out;
        }

        .subtitle {
            font-size: 1.2rem;
            color: #ffb3d1;
            margin-bottom: 25px;
        }

        .photo-frame {
            width: 200px;
            height: 200px;
            margin: 0 auto 25px auto;
            border-radius: 50%;
            overflow: hidden;
            border: 4px solid #ff65a3;
            box-shadow: 0 0 20px rgba(255, 101, 163, 0.5);
        }

        .photo-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .message-box {
            background: rgba(0, 0, 0, 0.3);
            padding: 20px;
            border-radius: 12px;
            margin-bottom: 25px;
            font-size: 1.05rem;
            line-height: 1.6;
            color: #fce4ec;
            border-left: 4px solid #ff65a3;
            text-align: left;
        }

        .countdown-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 25px;
        }

        .countdown-box {
            background: rgba(255, 105, 180, 0.1);
            padding: 10px 15px;
            border-radius: 8px;
            border: 1px solid rgba(255, 105, 180, 0.3);
            min-width: 60px;
        }

        .countdown-number {
            font-size: 1.5rem;
            font-weight: bold;
            color: #ff65a3;
        }

        .countdown-label {
            font-size: 0.75rem;
            color: #ffb3d1;
            text-transform: uppercase;
        }

        /* Floating background hearts animation */
        .hearts {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
            pointer-events: none;
        }

        .heart {
            position: absolute;
            display: block;
            width: 20px;
            height: 20px;
            background: rgba(255, 105, 180, 0.3);
            bottom: -20px;
            transform: rotate(45deg);
            animation: animateHeart 8s infinite linear;
        }

        .heart::before, .heart::after {
            content: '';
            width: 20px;
            height: 20px;
            background: rgba(255, 105, 180, 0.3);
            border-radius: 50%;
            position: absolute;
        }

        .heart::before {
            top: -10px;
            left: 0;
        }

        .heart::after {
            left: -10px;
            top: 0;
        }

        @keyframes animateHeart {
            0% {
                transform: translateY(0) rotate(45deg) scale(0.6);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(45deg) scale(1.2);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <!-- Floating Background Hearts -->
    <div class="hearts">
        <div class="heart" style="left: 10%; animation-duration: 7s;"></div>
        <div class="heart" style="left: 20%; animation-duration: 5s; animation-delay: 2s;"></div>
        <div class="heart" style="left: 35%; animation-duration: 9s; animation-delay: 1s;"></div>
        <div class="heart" style="left: 50%; animation-duration: 6s; animation-delay: 3s;"></div>
        <div class="heart" style="left: 65%; animation-duration: 8s; animation-delay: 0.5s;"></div>
        <div class="heart" style="left: 80%; animation-duration: 5.5s; animation-delay: 2.5s;"></div>
        <div class="heart" style="left: 90%; animation-duration: 7.5s; animation-delay: 1.5s;"></div>
    </div>

    <div class="container">
        <h1>Happy Birthday, Aami! ❤️</h1>
        <p class="subtitle">Wishing the most special person an incredible day filled with love and joy.</p>

        <!-- Photo element referencing your uploaded image -->
        <div class="photo-frame">
            <img src="IMG_9119.jpeg" alt="Aami">
        </div>

        <!-- Sweet Personal Note -->
        <div class="message-box">
            <p>To the one who brings so much warmth, light, and happiness into my world—Happy Birthday! May this year bring you endless smiles, success, and all the beautiful things your heart desires. Let's make this day unforgettable! ✨🥂</p>
        </div>

        <!-- Interactive Countdown / Timer Element -->
        <div class="countdown-container">
            <div class="countdown-box">
                <div class="countdown-number" id="days">00</div>
                <div class="countdown-label">Days</div>
            </div>
            <div class="countdown-box">
                <div class="countdown-number" id="hours">00</div>
                <div class="countdown-label">Hours</div>
            </div>
            <div class="countdown-box">
                <div class="countdown-number" id="minutes">00</div>
                <div class="countdown-label">Mins</div>
            </div>
            <div class="countdown-box">
                <div class="countdown-number" id="seconds">00</div>
                <div class="countdown-label">Secs</div>
            </div>
        </div>
    </div>

    <script>
        // Simple live timer script (Counts up from current moment or tracks celebration time)
        const birthdayDate = new Date().getTime(); // Can be customized to target a specific time
        
        setInterval(() => {
            const now = new Date().getTime();
            // Just a dynamic live seconds ticker or timer logic for interactivity
            const dateObj = new Date();
            document.getElementById('days').innerText = String(dateObj.getDate()).padStart(2, '0');
            document.getElementById('hours').innerText = String(dateObj.getHours()).padStart(2, '0');
            document.getElementById('minutes').innerText = String(dateObj.getMinutes()).padStart(2, '0');
            document.getElementById('seconds').innerText = String(dateObj.getSeconds()).padStart(2, '0');
        }, 1000);
    </script>
</body>
</html>

