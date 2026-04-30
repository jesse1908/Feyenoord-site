<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Feyenoord Fansite</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: #111;
    color: white;
}

/* HEADER */
header {
    background: linear-gradient(90deg, #d6001c, #000);
    padding: 20px;
    text-align: center;
}

/* NAV */
nav {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    background: black;
}

nav a {
    color: white;
    padding: 15px;
    text-decoration: none;
}

nav a:hover {
    background: #d6001c;
}

/* HERO */
.hero {
    padding: 60px 20px;
    text-align: center;
    background: url('https://upload.wikimedia.org/wikipedia/commons/7/7c/De_Kuip.jpg') center/cover;
}

.hero h1 {
    font-size: 3em;
    animation: fadeIn 2s ease-in-out;
}

/* CARDS */
.container {
    padding: 20px;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

.card {
    background: #1c1c1c;
    padding: 20px;
    border-radius: 10px;
    transition: transform 0.3s;
}

.card:hover {
    transform: scale(1.05);
}

/* LOGIN */
.login-box {
    max-width: 300px;
    margin: 30px auto;
    background: #222;
    padding: 20px;
    border-radius: 10px;
}

input {
    width: 100%;
    padding: 10px;
    margin: 5px 0;
}

button {
    background: #d6001c;
    border: none;
    padding: 10px;
    color: white;
    cursor: pointer;
    width: 100%;
}

button:hover {
    background: #a00015;
}

/* FOOTER */
footer {
    text-align: center;
    padding: 15px;
    background: black;
}

/* ANIMATIE */
@keyframes fadeIn {
    from {opacity: 0;}
    to {opacity: 1;}
}

/* RESPONSIVE */
@media (max-width: 600px) {
    .hero h1 {
        font-size: 2em;
    }
}
</style>
</head>

<body>

<header>
    <h1>Feyenoord Fansite</h1>
</header>

<nav>
    <a href="#">Home</a>
    <a href="#">Nieuws</a>
    <a href="#">Wedstrijden</a>
    <a href="#">Login</a>
</nav>

<section class="hero">
    <h1>Welkom in De Kuip 🔥</h1>
</section>

<div class="container">

    <div class="card">
        <h2>Laatste nieuws</h2>
        <p>Feyenoord wint weer! ⚽</p>
    </div>

    <div class="card">
        <h2>Live score</h2>
        <p id="score">Feyenoord 0 - 0 Ajax</p>
        <button onclick="updateScore()">Update score</button>
    </div>

    <div class="card">
        <h2>Fans</h2>
        <p>De beste supporters van Nederland ❤️🤍</p>
    </div>

</div>

<!-- LOGIN -->
<div class="login-box">
    <h2>Login</h2>
    <input type="text" id="username" placeholder="Gebruikersnaam">
    <input type="password" id="password" placeholder="Wachtwoord">
    <button onclick="login()">Login</button>
    <p id="loginResult"></p>
</div>

<footer>
    <p>© 2026 Feyenoord Fansite</p>
</footer>

<script>
// FAKE LIVE SCORE
function updateScore() {
    let goals1 = Math.floor(Math.random() * 5);
    let goals2 = Math.floor(Math.random() * 5);
    document.getElementById("score").innerText =
        "Feyenoord " + goals1 + " - " + goals2 + " Ajax";
}

// SIMPLE LOGIN
function login() {
    let user = document.getElementById("username").value;
    let pass = document.getElementById("password").value;

    if(user === "admin" && pass === "1234") {
        document.getElementById("loginResult").innerText = "Welkom!";
    } else {
        document.getElementById("loginResult").innerText = "Foute login!";
    }
}
</script>

</body>
</html>
