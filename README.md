<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LA Life Online</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: "Inter", "Segoe UI", Arial, sans-serif;
    color: #f2f2f2;
    background: #0b0b0b;
    line-height: 1.8;
}

/* NAVBAR */
nav {
    position: fixed;
    top: 0;
    width: 100%;
    background: rgba(10,10,10,0.8);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255,255,255,0.06);
    z-index: 1000;
}

nav ul {
    display: flex;
    justify-content: center;
    gap: 45px;
    padding: 22px;
    list-style: none;
}

nav a {
    color: #ffffff;
    text-decoration: none;
    font-size: 13px;
    letter-spacing: 2px;
    text-transform: uppercase;
    transition: 0.3s;
}

nav a:hover {
    color: #4f9cff;
}

/* HERO SECTION */
.hero {
    height: 100vh;
    position: relative;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.hero video {
    position: absolute;
    top: 50%;
    left: 50%;
    min-width: 100%;
    min-height: 100%;
    transform: translate(-50%, -50%);
    object-fit: cover;
    filter: brightness(0.35) blur(1px);
}

.hero-overlay {
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, rgba(15,15,20,0.6), rgba(15,15,20,0.9));
    z-index: 1;
}

.hero-content {
    position: relative;
    z-index: 2;
    padding: 0 20px;
    animation: fadeInUp 1.5s ease forwards;
}

.hero-content h1 {
    font-size: 72px;
    letter-spacing: 7px;
    margin-bottom: 20px;
    text-shadow: 0 0 20px rgba(79,156,255,0.6);
}

.hero-content p {
    font-size: 22px;
    max-width: 700px;
    color: #d0d0d0;
}

/* CONTAINER */
.container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 140px 30px 140px;
    display: flex;
    flex-direction: column;
    gap: 80px;
}

/* SECTIONS */
.section {
    background: rgba(20,20,30,0.65);
    border-radius: 20px;
    padding: 60px;
    box-shadow: 0 20px 50px rgba(0,0,0,0.6);
    backdrop-filter: blur(10px);
    opacity: 0;
    transform: translateY(40px);
    transition: all 0.8s ease;
}

.section.visible {
    opacity: 1;
    transform: translateY(0);
}

.section h2 {
    font-size: 36px;
    margin-bottom: 20px;
    letter-spacing: 2px;
    color: #ffffff;
}

.section p {
    font-size: 18px;
    color: #d0d0d0;
    line-height: 1.7;
}

.accent {
    border-left: 5px solid #4f9cff;
    padding-left: 30px;
}

/* FOOTER */
footer {
    margin-top: 80px;
    text-align: center;
    font-size: 14px;
    color: #888;
    padding: 40px 20px;
    background: rgba(10,10,10,0.7);
    backdrop-filter: blur(8px);
}

/* ANIMATIONS */
@keyframes fadeInUp {
    0% {
        opacity: 0;
        transform: translateY(40px);
    }
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}
</style>
</head>
<body>

<nav>
    <ul>
        <li><a href="#about">Start</a></li>
        <li><a href="#rules">Regeln</a></li>
        <li><a href="#factions">Fraktionen</a></li>
        <li><a href="#aboutus">Über uns</a></li>
    </ul>
</nav>

<!-- HERO -->
<div class="hero">
    <video autoplay muted loop>
        <source src="https://cdn.coverr.co/videos/coverr-los-angeles-sunset-1569/1080p.mp4" type="video/mp4">
    </video>
    <div class="hero-overlay"></div>
    <div class="hero-content">
        <h1>LA Life Online</h1>
        <p>Erlebe realistisches Roleplay auf einem neuen Level.</p>
    </div>
</div>

<div class="container">

    <div class="section" id="about">
        <h2>Real Life Experience</h2>
        <p>
            Tauche ein in eine dynamische Stadt voller Möglichkeiten.
            Wähle deinen eigenen Weg – legal oder illegal – und schreibe deine eigene Geschichte.
        </p>
    </div>

    <div class="section accent" id="rules">
        <h2>Regeln</h2>
        <p>
            Um ein faires und realistisches Spielerlebnis zu gewährleisten,
            haben wir klare Regeln für alle Spieler.
            Roleplay, Respekt und Konsequenz stehen an erster Stelle.
        </p>
    </div>

    <div class="section" id="factions">
        <h2>Fraktionen</h2>
        <p>
            Werde Teil spannender Fraktionen wie Polizei, Rettungsdienst oder Untergrundorganisationen.
            Jede Fraktion bietet einzigartige Aufgaben und Storymöglichkeiten.
        </p>
    </div>

    <div class="section accent" id="aboutus">
        <h2>Über uns</h2>
        <p>
            LA Life Online ist ein Roleplay-Projekt mit Fokus auf Realismus und Spielerfreiheit.
            Unsere Community legt Wert auf glaubwürdige Storys, Dynamik und langfristige Entwicklung.
        </p>
    </div>

    <footer>
        © 2026 LA Life Online – Alle Rechte vorbehalten
    </footer>

</div>

<script>
const sections = document.querySelectorAll('.section');
const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('visible');
        }
    });
}, { threshold: 0.2 });
sections.forEach(section => observer.observe(section));
</script>

</body>
</html>
