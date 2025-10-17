import zipfile
import os

# Folder and files setup in memory
folder_name = "/mnt/data/white-dragon-rys"
os.makedirs(folder_name + "/assets/css", exist_ok=True)
os.makedirs(folder_name + "/assets/js", exist_ok=True)
os.makedirs(folder_name + "/assets/img", exist_ok=True)

# File contents
files = {
    "index.html": """<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>White Dragon RYS — Home</title>
<link rel="stylesheet" href="assets/css/styles.css">
<script defer src="assets/js/script.js"></script>
</head>
<body>
<header class="site-header">
<div class="container">
<div class="brand">White Dragon RYS</div>
<nav class="nav">
<a href="index.html">Home</a>
<a href="about.html">About</a>
<a href="services.html">Services</a>
<a href="contact.html">Contact</a>
</nav>
<div class="lang-toggle">
<button id="lang-en">EN</button>
<button id="lang-bn">বাংলা</button>
</div>
</div>
</header>
<main class="container hero">
<div class="hero-left">
<h1>Hello! I'm White Dragon RYS</h1>
<p class="lead">The Dragon RYS — Web & App solutions</p>
<a class="btn" href="services.html">Our Services</a>
<a class="btn-outline" href="contact.html">Contact</a>
<ul class="quick-list">
<li>Web Design</li>
<li>App Development</li>
<li>Graphic Design</li>
</ul>
</div>
<div class="hero-right">
<img src="assets/img/avatar.jpg" alt="Avatar">
</div>
</main>
<footer class="site-footer">
<p>© White Dragon RYS — All rights reserved</p>
<p>Email: mohammedrifathossen1@gmail.com</p>
</footer>
</body>
</html>
""",
    "about.html": """<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>About — White Dragon RYS</title>
<link rel="stylesheet" href="assets/css/styles.css">
<script defer src="assets/js/script.js"></script>
</head>
<body>
<header class="site-header">
<div class="container">
<div class="brand">White Dragon RYS</div>
<nav class="nav">
<a href="index.html">Home</a>
<a href="about.html">About</a>
<a href="services.html">Services</a>
<a href="contact.html">Contact</a>
</nav>
<div class="lang-toggle">
<button id="lang-en-2">EN</button>
<button id="lang-bn-2">বাংলা</button>
</div>
</div>
</header>
<main class="container page about-grid">
<img src="assets/img/avatar.jpg" alt="Avatar">
<div>
<h2>About Me</h2>
<p>I build fast, modern websites and apps. I love solving problems and helping businesses grow online.</p>
<h3>Skills</h3>
<ul>
<li>HTML / CSS / JavaScript</li>
<li>React / Vite</li>
<li>Responsive Design</li>
<li>Design Tools</li>
</ul>
</div>
</main>
<footer class="site-footer">
<p>© White Dragon RYS</p>
</footer>
</body>
</html>
""",
    "services.html": """<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Services — White Dragon RYS</title>
<link rel="stylesheet" href="assets/css/styles.css">
<script defer src="assets/js/script.js"></script>
</head>
<body>
<header class="site-header">
<div class="container">
<div class="brand">White Dragon RYS</div>
<nav class="nav">
<a href="index.html">Home</a>
<a href="about.html">About</a>
<a href="services.html">Services</a>
<a href="contact.html">Contact</a>
</nav>
<div class="lang-toggle">
<button id="lang-en-3">EN</button>
<button id="lang-bn-3">বাংলা</button>
</div>
</div>
</header>
<main class="container page services-grid">
<article>
<h3>Web Design</h3>
<p>Clean, responsive websites for businesses and portfolios.</p>
</article>
<article>
<h3>App Development</h3>
<p>Mobile-first apps and progressive web apps (PWA).</p>
</article>
<article>
<h3>Graphic Design</h3>
<p>Logos, banners, social images, and marketing materials.</p>
</article>
<article>
<h3>AI Tools & Automation</h3>
<p>Automate repetitive tasks and boost productivity.</p>
</article>
<article>
<h3>Business Websites</h3>
<p>Multi-page sites for product & service businesses.</p>
</article>
<article>
<h3>Fast Landing Pages</h3>
<p>High-converting landing pages for campaigns.</p>
</article>
</main>
<footer class="site-footer">
<p>© White Dragon RYS</p>
</footer>
</body>
</html>
""",
    "contact.html": """<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Contact — White Dragon RYS</title>
<link rel="stylesheet" href="assets/css/styles.css">
<script defer src="assets/js/script.js"></script>
</head>
<body>
<header class="site-header">
<div class="container">
<div class="brand">White Dragon RYS</div>
<nav class="nav">
<a href="index.html">Home</a>
<a href="about.html">About</a>
<a href="services.html">Services</a>
<a href="contact.html">Contact</a>
</nav>
<div class="lang-toggle">
<button id="lang-en-4">EN</button>
<button id="lang-bn-4">বাংলা</button>
</div>
</div>
</header>
<main class="container page contact-page">
<h2>Contact</h2>
<form action="https://formspree.io/f/demo" method="POST">
<label>Name</label><input type="text" name="name" required>
<label>Email</label><input type="email" name="_replyto" required>
<label>Subject</label><input type="text" name="subject">
<label>Message</label><textarea name="message" rows="6"></textarea>
<button type="submit" class="btn">Send Message</button>
</form>
<p class="note">Or email directly: mohammedrifathossen1@gmail.com</p>
</main>
<footer class="site-footer">
<p>© White Dragon RYS</p>
</footer>
</body>
</html>
""",
    "assets/css/styles.css": "/* placeholder CSS */ body{font-family:sans-serif}",
    "assets/js/script.js": "// placeholder JS",
    "assets/img/avatar.jpg": b""  # empty placeholder image
}

# Write files
for path, content in files.items():
    full_path = os.path.join(folder_name, path)
    os.makedirs(os.path.dirname(full_path), exist_ok=True)
    mode = "wb" if isinstance(content, bytes) else "w"
    with open(full_path, mode) as f:
        f.write(content)

# Create ZIP
zip_path = "/mnt/data/white-dragon-rys.zip"
with zipfile.ZipFile(zip_path, 'w', zipfile.ZIP_DEFLATED) as zipf:
    for root, dirs, filenames in os.walk(folder_name):
        for filename in filenames:
            file_path = os.path.join(root, filename)
            zipf.write(file_path, os.path.relpath(file_path, folder_name))

zip_path
