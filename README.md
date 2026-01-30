<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Kim C Music | Sub Sound Box Records</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
:root{
  --main:#00ffd5;
  --dark:#050505;
  --soft:#0f0f0f;
  --text:#ffffff;
}
*{box-sizing:border-box;}
body{
  margin:0;
  font-family:Arial, Helvetica, sans-serif;
  background:var(--dark);
  color:var(--text);
  scroll-behavior:smooth;
}
nav{
  position:fixed;
  top:0;
  width:100%;
  background:rgba(0,0,0,0.9);
  padding:12px;
  text-align:center;
  z-index:1000;
}
nav a{
  color:white;
  margin:10px;
  text-decoration:none;
  font-weight:600;
}
section{
  padding:90px 10%;
  border-bottom:1px solid #111;
}
h1,h2{color:var(--main);}
.hero{
  min-height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  text-align:center;
  flex-direction:column;
}
.card{
  background:var(--soft);
  padding:25px;
  border-radius:18px;
  margin:15px 0;
}
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:20px;
}
button{
  padding:12px 20px;
  border:none;
  border-radius:8px;
  margin:5px;
  cursor:pointer;
  font-weight:600;
}
.pay{
  background:var(--main);
  color:black;
}
input,textarea{
  width:100%;
  padding:12px;
  margin:6px 0;
  border-radius:6px;
  border:none;
}
.footer{
  background:#000;
  padding:25px;
  text-align:center;
}
.badge{
  display:inline-block;
  background:#111;
  padding:6px 12px;
  border-radius:20px;
  margin:5px;
  font-size:13px;
}
</style>
</head>

<body>

<nav>
  <a href="#home">Home</a>
  <a href="#about">About</a>
  <a href="#music">Music</a>
  <a href="#beats">Beats</a>
  <a href="#services">Services</a>
  <a href="#studio">Studio</a>
  <a href="#gallery">Gallery</a>
  <a href="#stream">Streaming</a>
  <a href="#contact">Contact</a>
</nav>

<!-- HOME -->
<section id="home" class="hero">
  <h1>KIM C MUSIC</h1>
  <p><b>Artist • Producer • Songwriter • Vocal Coach</b></p>
  <p>Sub Sound Box Records</p>
  <p>Reggae • R&B • Dancehall</p>
  <div>
    <span class="badge">Music Store</span>
    <span class="badge">Beat Store</span>
    <span class="badge">Studio Booking</span>
    <span class="badge">Digital Payments</span>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <h2>Biography</h2>
  <div class="card">
    <p>
      <b>Kim C</b> (also styled as <b>Kim*C / Kim C UG</b>) is a Ugandan recording artist known for 
      Reggae, R&B and Dancehall. He is recognized for songs such as 
      <b>Kankyebeere (2021)</b>, <b>Kandye Ezange (2022)</b>, 
      <b>Ndabirwamu ft Vinka (2020)</b>, <b>Mpulila</b> from the Cassette project, 
      and earlier works like <b>Nkukutu</b> and <b>Nakoowa Obuzanyo</b>.
      <br><br>
      Founder of <b>Sub Sound Box Records</b>, Kim C is also a producer, songwriter, vocal coach, 
      and studio director. His music blends African rhythms with modern global sound, 
      creating a unique crossover style that connects Uganda to the world.
    </p>
  </div>
</section>

<!-- MUSIC STORE -->
<section id="music">
  <h2>Music Store</h2>
  <div class="grid">
    <div class="card">
      <b>Kankyebeere</b><br><br>
      <button class="pay">MTN Mobile Money</button>
      <button class="pay">Airtel Money</button>
      <button class="pay">Bank Card</button>
    </div>
    <div class="card">
      <b>Kandye Ezange</b><br><br>
      <button class="pay">MTN Mobile Money</button>
      <button class="pay">Airtel Money</button>
      <button class="pay">Bank Card</button>
    </div>
    <div class="card">
      <b>Ndabirwamu ft Vinka</b><br><br>
      <button class="pay">MTN Mobile Money</button>
      <button class="pay">Airtel Money</button>
      <button class="pay">Bank Card</button>
    </div>
  </div>
</section>

<!-- BEAT STORE -->
<section id="beats">
  <h2>Beat Store</h2>
  <div class="grid">
    <div class="card">
      <b>Afrobeat Beat</b><br><br>
      <button class="pay">MTN MoMo</button>
      <button class="pay">Airtel Money</button>
      <button class="pay">Bank Card</button>
    </div>
    <div class="card">
      <b>Dancehall Beat</b><br><br>
      <button class="pay">MTN MoMo</button>
      <button class="pay">Airtel Money</button>
      <button class="pay">Bank Card</button>
    </div>
    <div class="card">
      <b>R&B Beat</b><br><br>
      <button class="pay">MTN MoMo</button>
      <button class="pay">Airtel Money</button>
      <button class="pay">Bank Card</button>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <h2>Services</h2>
  <div class="grid">
    <div class="card">Music Production</div>
    <div class="card">Beat Production</div>
    <div class="card">Songwriting</div>
    <div class="card">Vocal Coaching</div>
    <div class="card">Artist Development</div>
    <div class="card">Mixing & Mastering</div>
    <div class="card">Studio Recording</div>
    <div class="card">Music Branding</div>
    <div class="card">Label Services</div>
  </div>
</section>

<!-- STUDIO -->
<section id="studio">
  <h2>Studio Booking</h2>
  <div class="card">
    <form>
      <input placeholder="Full Name">
      <input placeholder="Phone Number">
      <input placeholder="Email Address">
      <textarea placeholder="Session details"></textarea>
      <button class="pay" type="button">Book Studio Session</button>
    </form>
  </div>
</section>

<!-- GALLERY -->
<section id="gallery">
  <h2>Gallery</h2>
  <div class="card">
    Photos • Studio Sessions • Performances • Music Videos • Behind The Scenes
  </div>
</section>

<!-- STREAMING -->
<section id="stream">
  <h2>Streaming Platforms</h2>
  <div class="grid">
    <div class="card">YouTube</div>
    <div class="card">SoundCloud</div>
    <div class="card">Audiomack</div>
    <div class="card">Spotify</div>
    <div class="card">Boomplay</div>
    <div class="card">Mdundo</div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <h2>Contact & Location</h2>
  <div class="card">
    <p><b>Location:</b> Kampala, Uganda</p>
    <p><b>Label:</b> Sub Sound Box Records</p>
    <p><b>Email:</b> info@kimcmusic.com</p>
    <p><b>Payments:</b> MTN Mobile Money • Airtel Money • Visa • MasterCard</p>
    <p><b>Socials:</b> YouTube • Instagram • Facebook • SoundCloud</p>
  </div>
</section>

<div class="footer">
  <p>© 2026 Kim C Music | Sub Sound Box Records</p>
  <p>All Rights Reserved</p>
</div>

</body>
</html>

