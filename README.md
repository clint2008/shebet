# shebet
for her

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday! 🎂</title>

    <style>
        /* ===== BASIC PAGE DESIGN ===== */
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: "Trebuchet MS", Arial, sans-serif;
            text-align: center;
            color: #633d76;
            background: linear-gradient(
                135deg,
                #ffe0ed,
                #f1e3ff,
                #fff7e5
            );
            min-height: 100vh;
            overflow-x: hidden;
        }

        button {
            font-family: inherit;
        }

        /* ===== FLOATING BALLOONS ===== */
        .balloon {
            position: fixed;
            bottom: -150px;
            width: 48px;
            height: 62px;
            border-radius: 50%;
            opacity: 0.75;
            animation: floatUp 12s linear infinite;
            z-index: 0;
            pointer-events: none;
        }

        .balloon::after {
            content: "";
            position: absolute;
            width: 1px;
            height: 48px;
            background: #b78aa9;
            top: 60px;
            left: 50%;
        }

        .balloon:nth-child(1) {
            left: 7%;
            background: #ff8eb5;
            animation-delay: 0s;
        }

        .balloon:nth-child(2) {
            left: 82%;
            background: #b99aff;
            animation-delay: 3s;
        }

        .balloon:nth-child(3) {
            left: 48%;
            background: #ffd56f;
            animation-delay: 6s;
        }

        .balloon:nth-child(4) {
            left: 68%;
            background: #ffb6c9;
            animation-delay: 8s;
        }

        @keyframes floatUp {
            from {
                transform: translateY(0) rotate(-8deg);
            }
            to {
                transform: translateY(-120vh) rotate(12deg);
            }
        }

        /* ===== MAIN BIRTHDAY CARD ===== */
        .container {
            position: relative;
            z-index: 1;
            width: min(90%, 760px);
            margin: 45px auto;
            padding: 35px 22px;
            background: rgba(255, 255, 255, 0.83);
            border: 2px solid white;
            border-radius: 30px;
            box-shadow: 0 12px 40px rgba(125, 77, 150, 0.18);
        }

        .small-title {
            color: #b07bc9;
            font-size: 14px;
            letter-spacing: 4px;
            font-weight: bold;
        }

        h1 {
            margin: 15px 0;
            font-size: clamp(32px, 7vw, 58px);
            color: #e65e9b;
            text-shadow: 2px 3px 0 #ffe0ed;
        }

        .subtitle {
            font-size: 18px;
            line-height: 1.7;
            color: #80618e;
        }

        /* ===== BIRTHDAY PERSON'S NAME ===== */
        .birthday-name {
            font-size: clamp(30px, 6vw, 44px);
            color: #9b65c8;
            margin: 12px 0 22px;
            animation: nameGlow 2s ease-in-out infinite alternate;
        }

        @keyframes nameGlow {
            from {
                text-shadow: 0 0 4px #f6c5e1;
            }
            to {
                text-shadow: 0 0 18px #d7b6ff;
            }
        }

        /* ===== PROFILE PHOTO ===== */
        .photo-frame {
            width: 230px;
            height: 270px;
            max-width: 80%;
            margin: 20px auto;
            padding: 7px;
            border: 3px solid #e9bb69;
            border-radius: 28px;
            background: white;
            box-shadow: 0 8px 25px rgba(174, 111, 161, 0.25);
            overflow: hidden;
            transform: rotate(-2deg);
            transition: transform 0.4s ease;
        }

        .photo-frame:hover {
            transform: rotate(0deg) scale(1.04);
        }

        .photo-frame img {
            width: 100%;
            height: 100%;
            display: block;
            object-fit: cover;
            border-radius: 20px;
        }

        .photo-caption {
            font-size: 14px;
            color: #a47db2;
        }

        /* ===== BUTTONS ===== */
        .button-group {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
            margin: 25px 0;
        }

        .btn {
            border: none;
            border-radius: 30px;
            padding: 13px 20px;
            color: white;
            background: linear-gradient(135deg, #ee80b1, #ad80e7);
            font-size: 15px;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 5px 14px rgba(174, 111, 190, 0.2);
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 18px rgba(174, 111, 190, 0.35);
        }

        .btn:active {
            transform: scale(0.97);
        }

        .btn-gold {
            color: #795321;
            background: linear-gradient(135deg, #ffe6a0, #ffcb70);
        }

        /* ===== BIRTHDAY LETTER ===== */
        .letter {
            display: none;
            margin: 25px auto;
            padding: 25px;
            max-width: 560px;
            text-align: left;
            line-height: 1.9;
            background: #fff8fc;
            border: 2px dashed #e7a4ca;
            border-radius: 20px;
        }

        .letter.show {
            display: block;
            animation: letterOpen 0.7s ease both;
        }

        .letter h2 {
            text-align: center;
            color: #df6da4;
        }

        @keyframes letterOpen {
            from {
                opacity: 0;
                transform: translateY(20px) scale(0.95);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        /* ===== HIDDEN SURPRISE ===== */
        .surprise {
            display: none;
            margin: 25px auto;
            padding: 24px;
            background: #fff0c9;
            border-radius: 20px;
            animation: letterOpen 0.6s ease both;
        }

        .surprise.show {
            display: block;
        }

        .surprise .big-heart {
            font-size: 55px;
            animation: heartbeat 1s infinite;
        }

        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.15);
            }
        }

        /* ===== CONFETTI ===== */
        #confetti-canvas {
            position: fixed;
            inset: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 10;
        }

        footer {
            position: relative;
            z-index: 1;
            padding: 10px 15px 30px;
            color: #9b7aa6;
            font-size: 14px;
        }

        /* ===== MOBILE DESIGN ===== */
        @media (max-width: 480px) {
            .container {
                margin: 20px auto;
                padding: 28px 16px;
            }

            .subtitle {
                font-size: 16px;
            }

            .photo-frame {
                width: 210px;
                height: 245px;
            }

            .btn {
                width: 100%;
                max-width: 280px;
            }

            .letter {
                padding: 18px;
            }
        }

        /* Respect reduced-motion preferences */
        @media (prefers-reduced-motion: reduce) {
            *, *::before, *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                scroll-behavior: auto !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>

<body>

    <!-- Floating decorative balloons -->
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>

    <!-- Confetti will be drawn on this canvas -->
    <canvas id="confetti-canvas"></canvas>

    <main class="container">

        <p class="small-title">A SPECIAL DAY JUST FOR YOU</p>

        <h1>Happy Birthday! 🎂</h1>

        <p class="subtitle">
            Today is all about celebrating someone truly special.
        </p>

        <!-- Change this to the birthday person's name -->
        <h2 class="birthday-name" id="birthdayName">
            Birthday Star 💗
        </h2>

        <!-- Put your picture in the same folder as this HTML file -->
        <div class="photo-frame">
            <img
                src="birthday-photo.jpg"
                alt="Birthday person's photo"
                id="birthdayPhoto"
            >
        </div>

        <p class="photo-caption">
            ✨ A beautiful soul deserves a beautiful day ✨
        </p>

        <p class="subtitle">
            Wishing you a day filled with love, laughter, and sweet memories!
        </p>

        <div class="button-group">
            <button class="btn" id="messageButton">
                Open Your Birthday Message 💌
            </button>

            <button class="btn btn-gold" id="celebrateButton">
                Celebrate! 🎉
            </button>

            <button class="btn" id="surpriseButton">
                Reveal Your Surprise 🎁
            </button>
        </div>

        <!-- Birthday letter: edit this message whenever you like -->
        <section class="letter" id="birthdayLetter">
            <h2>💌 A Letter Just for You 💌</h2>

            <p>Dear <span id="letterName">Birthday Star</span>,</p>

            <p>
                Happy Birthday! 💗 I hope your special day brings you
                endless happiness, beautiful memories, and so many reasons
                to smile.
            </p>

            <p>
                May you continue to grow, discover wonderful things,
                and achieve the dreams that mean the most to you.
                Always remember that you deserve kindness, love,
                and all the good things life has to offer.
            </p>

            <p>
                Thank you for being the wonderful person you are.
                May this new chapter of your life be full of exciting
                adventures, genuine laughter, and unforgettable moments.
            </p>

            <p>
                Enjoy every second of your special day.
                You deserve to feel celebrated today and every day! 🎂✨
            </p>

            <p>With lots of love,</p>
            <p><strong>Someone who wishes you the best 💕</strong></p>
        </section>

        <!-- Hidden until the surprise button is clicked -->
        <section class="surprise" id="birthdaySurprise">
            <div class="big-heart">💖</div>
            <h2>Surprise! 🎉</h2>

            <p>
                Your gift is a little reminder that you are appreciated,
                celebrated, and wished nothing but wonderful things.
            </p>

            <p>
                May your wishes come true, one beautiful moment at a time! 🌟
            </p>

            <p>🎁 Sending you the biggest birthday hug! 🎁</p>
        </section>

        <!-- Background music controls -->
        <div>
            <p>🎵 Add a little music to the celebration 🎵</p>

            <div class="button-group">
                <button class="btn" id="musicButton">
                    ▶ Play Birthday Music
                </button>
            </div>

            <p class="photo-caption" id="musicStatus">
                Add your music file to enable playback.
            </p>
        </div>

    </main>

    <footer>
        Made with 💗, confetti, and birthday wishes.
    </footer>

    <script>
        // ==========================================
        // 1. PERSONALIZE THE BIRTHDAY GREETING HERE
        // ==========================================

        const personName = "Birthday Star";

        // Change the name above, for example:
        // const personName = "Maria";

        document.getElementById("birthdayName").textContent = personName + " 💗";
        document.getElementById("letterName").textContent = personName;


        // ==========================================
        // 2. OPEN AND CLOSE THE BIRTHDAY LETTER
        // ==========================================

        const messageButton = document.getElementById("messageButton");
        const birthdayLetter = document.getElementById("birthdayLetter");

        messageButton.addEventListener("click", function () {
            birthdayLetter.classList.toggle("show");

            if (birthdayLetter.classList.contains("show")) {
                messageButton.textContent = "Close Birthday Message 💌";
                birthdayLetter.scrollIntoView({
                    behavior: "smooth",
                    block: "nearest"
                });
            } else {
                messageButton.textContent = "Open Your Birthday Message 💌";
            }
        });


        // ==========================================
        // 3. REVEAL THE HIDDEN SURPRISE
        // ==========================================

        const surpriseButton = document.getElementById("surpriseButton");
        const birthdaySurprise = document.getElementById("birthdaySurprise");

        surpriseButton.addEventListener("click", function () {
            birthdaySurprise.classList.toggle("show");

            if (birthdaySurprise.classList.contains("show")) {
                surpriseButton.textContent = "Hide Surprise 🎁";
                launchConfetti();

                birthdaySurprise.scrollIntoView({
                    behavior: "smooth",
                    block: "nearest"
                });
            } else {
                surpriseButton.textContent = "Reveal Your Surprise 🎁";
            }
        });


        // ==========================================
        // 4. CONFETTI ANIMATION
        // ==========================================

        const canvas = document.getElementById("confetti-canvas");
        const ctx = canvas.getContext("2d");

        let confettiPieces = [];
        let animationRunning = false;

        // Make the canvas fit the screen
        function resizeCanvas() {
            const ratio = window.devicePixelRatio || 1;

            canvas.width = window.innerWidth * ratio;
            canvas.height = window.innerHeight * ratio;

            canvas.style.width = window.innerWidth + "px";
            canvas.style.height = window.innerHeight + "px";

            ctx.setTransform(ratio, 0, 0, ratio, 0, 0);
        }

        window.addEventListener("resize", resizeCanvas);
        resizeCanvas();

        // Create colorful confetti pieces
        function launchConfetti() {
            const colors = [
                "#ff70a6",
                "#b388ff",
                "#ffd166",
                "#ffffff",
                "#ff9f1c",
                "#8bd3dd"
            ];

            for (let i = 0; i < 160; i++) {
                confettiPieces.push({
                    x: Math.random() * window.innerWidth,
                    y: -Math.random() * window.innerHeight,
                    size: Math.random() * 8 + 4,
                    speed: Math.random() * 4 + 2,
                    drift: Math.random() * 3 - 1.5,
                    color: colors[Math.floor(Math.random() * colors.length)],
                    rotation: Math.random() * 360
                });
            }

            if (!animationRunning) {
                animationRunning = true;
                animateConfetti();
            }
        }

        function animateConfetti() {
            ctx.clearRect(0, 0, window.innerWidth, window.innerHeight);

            confettiPieces.forEach(function (piece) {
                piece.y += piece.speed;
                piece.x += piece.drift;
                piece.rotation += 4;

                ctx.save();
                ctx.translate(piece.x, piece.y);
                ctx.rotate(piece.rotation * Math.PI / 180);
                ctx.fillStyle = piece.color;
                ctx.fillRect(
                    -piece.size / 2,
                    -piece.size / 2,
                    piece.size,
                    piece.size * 0.65
                );
                ctx.restore();
            });

            // Remove confetti that has fallen off the screen
            confettiPieces = confettiPieces.filter(function (piece) {
                return piece.y < window.innerHeight + 20;
            });

            if (confettiPieces.length > 0) {
                requestAnimationFrame(animateConfetti);
            } else {
                animationRunning = false;
                ctx.clearRect(0, 0, window.innerWidth, window.innerHeight);
            }
        }

        document.getElementById("celebrateButton").addEventListener(
            "click",
            launchConfetti
        );


        // ==========================================
        // 5. BACKGROUND BIRTHDAY MUSIC
        // ==========================================

        // Put a music file named birthday-music.mp3 beside this HTML file.
        const birthdayMusic = new Audio("birthday-music.mp3");
        birthdayMusic.loop = true;

        const musicButton = document.getElementById("musicButton");
        const musicStatus = document.getElementById("musicStatus");

        musicButton.addEventListener("click", async function () {
            if (birthdayMusic.paused) {
                try {
                    await birthdayMusic.play();

                    musicButton.textContent = "⏸ Pause Birthday Music";
                    musicStatus.textContent = "Music is playing. Enjoy! 🎵";
                } catch (error) {
                    musicStatus.textContent =
                        "Music could not play. Check your music filename and try again.";
                }
            } else {
                birthdayMusic.pause();

                musicButton.textContent = "▶ Play Birthday Music";
                musicStatus.textContent = "Music paused.";
            }
        });
    </script>

</body>
</html>
