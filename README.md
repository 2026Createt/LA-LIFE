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
    background: rgba(10,10,10,0.85);
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
}

nav a:hover {
    color: #4f9cff;
}

/* HERO VIDEO */
.hero {
    height: 100vh;
    position: relative;
    overflow: hidden;
}

.hero video {
    position: absolute;
    top: 50%;
    left: 50%;
    min-width: 100%;
    min-height: 100%;
    transform: translate(-50%, -50%);
    object-fit: cover;
    filter: brightness(0.35);
}

.hero-content {
    position: relative;
    z-index: 2;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 0 30px;
}

.hero-content h1 {
    font-size: 68px;
    letter-spacing: 7px;
    margin-bottom: 20px;
}

.hero-content p {
    font-size: 20px;
    color: #d0d0d0;
    max-width: 700px;
}

/* CONTAINER */
.container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 140px 30px 140px;
}

/* SECTIONS */
.section {
    background: rgba(15,15,15,0.88);
    border-radius: 16px;
    padding: 60px;
    margin-bottom: 80px;
    box-shadow: 0 30px 70px rgba(0,0,0,0.45);
    opacity: 0;
    transform: translateY(40px);
    transition: all 0.8s ease;
}

.section.visible {
    opacity: 1;
    transform: translateY(0);
}

.section h2 {
    font-size: 30px;
    margin-bottom: 25px;
    letter-spacing: 2px;
}

.section p {
    font-size: 17px;
    color: #e2e2e2;
}

.accent {
    border-left: 4px solid #4f9cff;
    padding-left: 30px;
}

/* FOOTER */
footer {
    margin-top: 140px;
    text-align: center;
    font-size: 14px;
    color: #aaaaaa;
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
