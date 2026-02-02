.<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Cutie 🖤</title>

<!-- 🖋️ Calligraphy Font -->
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
* { box-sizing: border-box; }

body {
    margin: 0;
    min-height: 100vh;
    width: 100vw;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    background: radial-gradient(circle at top, #2b0a1f, #000);
    font-family: 'Poppins', sans-serif;
    color: white;
}

/* Floating hearts */
.heart {
    position: absolute;
    bottom: -20px;
    animation: floatUp 6s linear infinite;
    opacity: 0.8;
}

@keyframes floatUp {
    0% { transform: translateY(0) scale(1); opacity: 1; }
    100% { transform: translateY(-120vh) scale(1.6); opacity: 0; }
}

/* Card */
.card {
    width: 90%;
    max-width: 420px;
    background: rgba(20, 20, 20, 0.95);
    padding: 25px;
    border-radius: 25px;
    text-align: center;
    box-shadow: 0 0 40px rgba(255, 0, 100, 0.4);
    z-index: 10;
    animation: fadeIn 1.5s ease-in-out;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

/* 🖋️ Calligraphy Headings */
h1, h2 {
    font-family: 'Great Vibes', cursive;
    color: #ff4b6e;
    font-size: 2.2rem;
    margin-bottom: 10px;
}

.name {
    color: #ff4b6e;
    font-weight: bold;
}

/* Photo fade-in */
.photo {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    object-fit: cover;
    border: 4px solid #ff4b6e;
    margin: 15px 0;
    box-shadow: 0 0 20px rgba(255,75,110,0.7);
    opacity: 0;
    animation: photoFade 2.5s ease forwards;
    animation-delay: 2s;
}

@keyframes photoFade {
    from { opacity: 0; transform: scale(0.9); }
    to { opacity: 1; transform: scale(1); }
}

/* 💌 Typing love letter – calligraphy */
#typing {
    min-height: 100px;
    font-family: 'Great Vibes', cursive;
    font-size: 1.5rem;
    line-height: 1.6;
    margin-bottom: 15px;
    color: #ffd6e3;
}

/* Buttons */
.buttons {
    display: none;
}

button {
    padding: 12px 26px;
    font-size: 16px;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    margin: 8px;
    transition: 0.3s;
    font-family: 'Poppins', sans-serif;
}

.yes {
    background: linear-gradient(135deg, #ff4b6e, #ff758c);
    color: white;
    box-shadow: 0 0 15px rgba(255,75,110,0.8);
}

.no {
    background-color: #444;
    color: #ccc;
}

button:hover {
    transform: scale(1.1);
}

/* Heart burst */
.burst-heart {
    position: absolute;
    font-size: 22px;
    animation: burst 1.2s ease-out forwards;
    pointer-events: none;
}

@keyframes burst {
    from { transform: scale(0); opacity: 1; }
    to { transform: translate(var(--x), var(--y)) scale(1.6); opacity: 0; }
}

/* Ring animation */
.ring {
    position: fixed;
    font-size: 70px;
    animation: ringPop 1.5s ease-out forwards;
    pointer-events: none;
}

@keyframes ringPop {
    0% { transform: scale(0); opacity: 0; }
    50% { transform: scale(1.4); opacity: 1; }
    100% { transform: scale(1); opacity: 0; }
}
</style>
</head>

<body>

<!-- 🎶 Music -->
<audio autoplay loop>
    <source src="romantic-music.mp3" type="audio/mpeg">
</audio>

<div class="card">
    <h1>Happy Valentine’s Day</h1>

    <img src="her-photo.jpg" class="photo" alt="My Cutie">

    <p>Hey <span class="name">MINE CUTIE RASMALAI</span> 🥰</p>

    <!-- Typing Love Letter -->
    <div id="typing"></div>

    <!-- Question -->
    <div class="buttons" id="buttons">
        <h2>Will you be my Better Half?</h2>
        <button class="yes" onclick="sayYes(event)">YES 💕</button>
        <button class="no" onclick="sayNo()">NO 🙈</button>
    </div>
</div>

<script>
/* Typing Effect */
const text = `In a world full of noise,
you became my calm.
In moments of darkness,
you became my light.

I don’t promise perfection,
but I promise love,
respect, and a lifetime
of choosing you 🖤`;

let i = 0;
const typingDiv = document.getElementById("typing");
const buttons = document.getElementById("buttons");

function typeText() {
    if (i < text.length) {
        typingDiv.innerHTML += text.charAt(i);
        i++;
        setTimeout(typeText, 40);
    } else {
        buttons.style.display = "block";
    }
}
typeText();

/* Floating hearts */
setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (15 + Math.random() * 25) + "px";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 7000);
}, 300);

/* YES click */
function sayYes(e) {
    heartBurst(e.clientX, e.clientY);
    ringAnimation();
    heartbeatVibration();
    setTimeout(() => {
        alert("YAY!!! ❤️\n\nYou are my forever.\nHappy Valentine’s Day, my Better Half 🖤");
    }, 900);
}

function sayNo() {
    alert("😌 It’s okay… my heart already chose you 🖤");
}

/* Heart burst */
function heartBurst(x, y) {
    for (let j = 0; j < 25; j++) {
        const h = document.createElement("div");
        h.className = "burst-heart";
        h.innerHTML = "❤️";
        h.style.left = x + "px";
        h.style.top = y + "px";
        const angle = Math.random() * 2 * Math.PI;
        const distance = 80 + Math.random() * 60;
        h.style.setProperty("--x", Math.cos(angle) * distance + "px");
        h.style.setProperty("--y", Math.sin(angle) * distance + "px");
        document.body.appendChild(h);
        setTimeout(() => h.remove(), 1200);
    }
}

/* Ring */
function ringAnimation() {
    const ring = document.createElement("div");
    ring.className = "ring";
    ring.innerHTML = "💍";
    ring.style.top = "50%";
    ring.style.left = "50%";
    ring.style.transform = "translate(-50%, -50%)";
    document.body.appendChild(ring);
    setTimeout(() => ring.remove(), 1500);
}

/* Heartbeat vibration (mobile) */
function heartbeatVibration() {
    if (navigator.vibrate) {
        navigator.vibrate([150, 100, 150, 100, 300]);
    }
}
</script>

</body>
</html>
