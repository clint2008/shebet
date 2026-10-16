
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday!</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    color: #603b69;
    background: linear-gradient(135deg, #ffe4ef, #eee3ff, #fff8df);
    text-align: center;
}

header {
    padding: 50px 15px 30px;
}

h1 {
    color: #e34d98;
    font-size: clamp(2.5rem, 8vw, 4.5rem);
    margin-bottom: 10px;
    text-shadow: 2px 3px white;
}

h2 {
    color: #a34bc0;
}

p {
    line-height: 1.7;
}

.container {
    width: 92%;
    max-width: 1050px;
    margin: auto;
}

.card {
    background: rgba(255, 255, 255, 0.9);
    padding: 25px;
    margin: 25px 0;
    border-radius: 24px;
    box-shadow: 0 8px 25px #8c5a991c;
}

.main-photo {
    width: 100%;
    max-width: 350px;
    height: 350px;
    object-fit: cover;
    border: 6px solid white;
    border-radius: 22px;
    background: #f8d8eb;
}

button {
    border: none;
    border-radius: 25px;
    padding: 13px 20px;
    margin: 6px;
    font-size: 15px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.2s;
}

button:hover {
    transform: translateY(-2px);
}

.pink {
    background: #ec66a6;
    color: white;
}

.purple {
    background: #b89bea;
    color: white;
}

.gold {
    background: #ffe08a;
    color: #684b19;
}

.gallery {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 15px;
}

.photo-card {
    padding: 6px;
    background: white;
    border-radius: 15px;
    box-shadow: 0 5px 15px #603b6915;
    overflow: hidden;
}

.photo-card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
    border-radius: 10px;
    cursor: pointer;
}

.caption {
    padding: 8px 2px;
    font-size: 14px;
}

.letter {
    display: none;
    background: #fff4fa;
    padding: 22px;
    border-radius: 15px;
    white-space: pre-line;
    line-height: 1.9;
}

.surprise {
    display: none;
    padding: 20px;
    background: #fff1f8;
    border-radius: 15px;
    font-size: 20px;
}

.balloons span {
    position: fixed;
    bottom: -100px;
    font-size: 40px;
    z-index: -1;
    animation: floatUp 12s linear infinite;
}

.balloons span:nth-child(1) {
    left: 5%;
}

.balloons span:nth-child(2) {
    left: 25%;
    animation-delay: 3s;
}

.balloons span:nth-child(3) {
    right: 20%;
    animation-delay: 5s;
}

.balloons span:nth-child(4) {
    right: 5%;
    animation-delay: 1s;
}

@keyframes floatUp {
    from {
        transform: translateY(0);
    }
    to {
        transform: translateY(-120vh);
    }
}

footer {
    padding: 30px 10px;
}

#lightbox {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 10;
    background: #160c20ee;
    align-items: center;
    justify-content: center;
    padding: 20px;
}

#lightbox img {
    max-width: 95%;
    max-height: 80vh;
    object-fit: contain;
    border-radius: 15px;
}

#closeLightbox {
    position: absolute;
    top: 15px;
    right: 15px;
}

@media (max-width: 750px) {
    .gallery {
        grid-template-columns: repeat(3, 1fr);
    }
}

@media (max-width: 450px) {
    .gallery {
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
    }

    .photo-card img {
        height: 140px;
    }

    .card {
        padding: 16px;
    }
}
</style>
</head>

<body>

<div class="balloons">
    <span>🎈</span>
    <span>🎈</span>
    <span>🎈</span>
    <span>🎈</span>
</div>

<header>
    <h1>🎂 Happy Birthday! 🎉</h1>
    <p>A special day for someone truly special. 💗</p>
</header>

<main class="container">

    <section class="card">
        <img
            class="main-photo"
            src="photos/photo1.jpg"
            alt="Birthday photo"
            onerror="this.alt='Add your main photo as photos/photo1.jpg';"
        >

        <h2>To: <span id="birthdayName">Your Special Someone</span> 💖</h2>

        <p>
            May your birthday be filled with happiness, laughter,
            love, and wonderful memories. May all your dreams
            come true and may this new chapter bring you success!
        </p>

        <button class="pink" onclick="celebrate()">
            🎊 Celebrate!
        </button>

        <button class="purple" onclick="toggleLetter()">
            💌 Open Birthday Letter
        </button>
    </section>

    <section class="card">
        <h2>📸 Our Favorite Memories</h2>
        <p>Ten photos, countless memories! 💗</p>

        <div class="gallery" id="gallery"></div>
    </section>

    <section class="card">
        <h2>💌 A Birthday Letter for You</h2>

        <div class="letter" id="letter">
Happy Birthday! 💖

I hope your special day brings you endless happiness,
beautiful memories, and lots of reasons to smile.

Thank you for being such a wonderful person.
May you achieve your dreams and always find
reasons to be happy.

Enjoy your special day. You deserve the best!

With love,
Someone who cares 💗
        </div>
    </section>

    <section class="card">
        <h2>🎁 A Little Surprise</h2>

        <button class="gold" onclick="showSurprise()">
            Open Your Surprise ✨
        </button>

        <div class="surprise" id="surprise">
            💖 You are special, appreciated, and loved!
            May your wishes come true and your year
            be full of beautiful beginnings. 🎂
        </div>
    </section>

</main>

<footer>
    Made with 💗 just for your special day!
</footer>

<div id="lightbox" onclick="closePhoto(event)">
    <button id="closeLightbox" class="gold">✖ Close</button>
    <img id="largePhoto" src="" alt="Enlarged birthday memory">
</div>

<script>
// CHANGE THIS TO THE BIRTHDAY CELEBRANT'S NAME
const birthdayName = "Your Special Someone";

document.getElementById("birthdayName").textContent = birthdayName;

// PHOTOS MUST BE INSIDE A FOLDER NAMED "photos"
const photos = [
    "photo1.jpg",
    "photo2.jpg",
    "photo3.jpg",
    "photo4.jpg",
    "photo5.jpg",
    "photo6.jpg",
    "photo7.jpg",
    "photo8.jpg",
    "photo9.jpg",
    "photo10.jpg"
];

const gallery = document.getElementById("gallery");

photos.forEach(function(file, index) {
    const card = document.createElement("div");
    card.className = "photo-card";

    const image = document.createElement("img");
    image.src = "photos/" + file;
    image.alt = "Birthday memory " + (index + 1);

    image.onerror = function() {
        this.alt = file + " not found";
        this.style.opacity = "0.3";
    };

    image.onclick = function() {
        if (image.naturalWidth > 0) {
            document.getElementById("largePhoto").src = image.src;
            document.getElementById("lightbox").style.display = "flex";
        }
    };

    const caption = document.createElement("div");
    caption.className = "caption";
    caption.textContent = "Memory " + (index + 1);

    card.appendChild(image);
    card.appendChild(caption);
    gallery.appendChild(card);
});

function celebrate() {
    const emojis = ["🎉", "💖", "✨", "🎊", "💗"];

    for (let i = 0; i < 60; i++) {
        const piece = document.createElement("span");

        piece.textContent =
            emojis[Math.floor(Math.random() * emojis.length)];

        piece.style.position = "fixed";
        piece.style.left = Math.random() * 100 + "vw";
        piece.style.top = "-30px";
        piece.style.fontSize = "25px";
        piece.style.zIndex = "20";
        piece.style.pointerEvents = "none";
        piece.style.transition = "transform 3s, opacity 3s";

        document.body.appendChild(piece);

        requestAnimationFrame(function() {
            piece.style.transform =
                "translateY(110vh) rotate(500deg)";
            piece.style.opacity = "0";
        });

        setTimeout(function() {
            piece.remove();
        }, 3100);
    }
}

function toggleLetter() {
    const letter = document.getElementById("letter");

    if (letter.style.display === "block") {
        letter.style.display = "none";
    } else {
        letter.style.display = "block";
        letter.scrollIntoView({
            behavior: "smooth",
            block: "center"
        });
    }
}

function showSurprise() {
    const surprise = document.getElementById("surprise");

    if (surprise.style.display === "block") {
        surprise.style.display = "none";
    } else {
        surprise.style.display = "block";
    }
}

function closePhoto(event) {
    if (event.target.id === "lightbox" ||
        event.target.id === "closeLightbox") {
        document.getElementById("lightbox").style.display = "none";
        document.getElementById("largePhoto").src = "";
    }
}
</script>

</body>
</html>
