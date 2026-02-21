
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LA Life</title>
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
    line-height: 1.8;
    background: url("hintergrund.png") center center / cover no-repeat fixed;
}

/* DARK OVERLAY OVER BACKGROUND */
body::before {
    content: "";
    position: fixed;
    inset: 0;
    background: linear-gradient(180deg, rgba(10,10,15,0.75), rgba(10,10,15,0.95));
    backdrop-filter: blur(4px);
    z-index: -1;
}

/* NAVBAR */
nav {
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    top: 0;
    width: 100%;
    background: rgba(10,10,10,0.6);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255,255,255,0.08);
    z-index: 1000;
    padding: 12px 50px;
}

nav .logo {
    position: absolute;
    left: 50px;
}

nav .logo img {
    height: 40px;
    width: auto;
}

nav ul {
    display: flex;
    gap: 45px;
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

/* HERO */
.hero {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 0 20px;
}

.hero-content h1 {
    font-size: 72px;
    letter-spacing: 7px;
    margin-bottom: 20px;
    text-shadow: 0 0 25px rgba(0,0,0,0.8);
}

.hero-content p {
    font-size: 22px;
    max-width: 700px;
    margin: 0 auto 30px;
    color: #dcdcdc;
}

/* DISCORD BUTTON */
.invite-btn {
    display: inline-block;
    padding: 16px 50px;
    font-size: 18px;
    font-weight: 600;
    border-radius: 50px;
    background: #7289da;
    color: #ffffff;
    text-decoration: none;
    transition: 0.3s ease;
    box-shadow: 0 8px 25px rgba(114,137,218,0.5);
}

.invite-btn:hover {
    transform: translateY(-4px) scale(1.05);
    box-shadow: 0 12px 35px rgba(114,137,218,0.7);
    background: #5b6eae;
}

/* CONTAINER */
.container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 140px 30px;
    display: flex;
    flex-direction: column;
    gap: 80px;
}

/* SECTIONS */
.section {
    background: rgba(20,20,30,0.55);
    border-radius: 20px;
    padding: 60px;
    box-shadow: 0 25px 60px rgba(0,0,0,0.6);
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
}

.section p {
    font-size: 18px;
    color: #e2e2e2;
}

.accent {
    border-left: 5px solid #4f9cff;
    padding-left: 30px;
}

/* FOOTER */
footer {
    text-align: center;
    font-size: 14px;
    color: #aaa;
    padding: 60px 20px;
}
</style>
</head>

<body>

<nav>
    <div class="logo">
        <img src="la_life.png" alt="LA Life Online Logo">
    </div>
    <ul>
        <li><a href="#about">Start</a></li>
        <li><a href="#rules">Regeln</a></li>
        <li><a href="#factions">Fraktionen</a></li>
        <li><a href="#aboutus">Über uns</a></li>
    </ul>
</nav>

<div class="hero">
    <div class="hero-content">
        <h1>LA Life</h1>
        <p>Erlebe realistisches Roleplay auf einem neuen Level.</p>
        <a href="https://discord.gg/la-life" target="_blank" class="invite-btn">LA@Life Discord beitreten</a>
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
            LA Life  ist ein Roleplay-Projekt mit Fokus auf Realismus und Spielerfreiheit.
            Unsere Community legt Wert auf glaubwürdige Storys, Dynamik und langfristige Entwicklung.
        </p>
    </div>

</div>

<footer>
    © 2026 LA Life – Alle Rechte vorbehalten.
</footer>

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
