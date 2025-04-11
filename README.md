# CSS Layouts and Responsive Design

## Objectives

Implement Flexbox and Grid for layout design.
Make the webpage responsive using media queries.
Ensure proper alignment and spacing.

## Instructions

- use Flexbox or CSS Grid.
- Add a navigation bar and structure the content.
- Use media queries to adjust layout for mobile, tablet, and desktop.

>[!NOTE]
>  - Include at least:
>  - navigation bar
>  - media queries

# Tasks

- Apply Flexbox or Grid for layout.
- Make the page responsive.
- Test across different screen sizes.

Happy Coding! 💻✨

### My answer starts here!

## index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Layout</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav class="navbar">
            <div class="logo">WebDevPro</div>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Services</a></li>
                <li><a href="#">Projects</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
            <div class="burger">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
        </nav>
    </header>

    <main class="container">
        <section class="hero">
            <h1>Welcome to WebDevPro</h1>
            <p>Your partner in building modern and responsive websites.</p>
            <button class="cta-button">Explore Services</button>
        </section>

        <section class="features">
            <article class="feature-card">
                <h2>Custom Websites</h2>
                <p>We design and develop tailored websites to match your brand and goals.</p>
            </article>
            <article class="feature-card">
                <h2>Responsive Design</h2>
                <p>Our layouts adapt seamlessly to all screen sizes and devices.</p>
            </article>
            <article class="feature-card">
                <h2>SEO & Performance</h2>
                <p>We optimize your website for search engines and fast load times.</p>
            </article>
        </section>

        <section class="gallery">
            <div class="gallery-item">Landing Page</div>
            <div class="gallery-item">E-commerce Site</div>
            <div class="gallery-item">Portfolio Site</div>
            <div class="gallery-item">Blog Layout</div>
            <div class="gallery-item">Dashboard UI</div>
            <div class="gallery-item">Mobile App UI</div>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 WebDevPro. All rights reserved.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>


## styles.css


* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
}


.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background-color: #2c3e50;
    color: white;
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
}

.nav-links {
    display: flex;
    list-style: none;
}

.nav-links li {
    margin-left: 2rem;
}

.nav-links a {
    color: white;
    text-decoration: none;
    transition: color 0.3s;
}

.nav-links a:hover {
    color: #3498db;
}

.burger {
    display: none;
    cursor: pointer;
}

.burger div {
    width: 25px;
    height: 3px;
    background-color: white;
    margin: 5px;
    transition: all 0.3s ease;
}


.container {
    display: grid;
    grid-template-areas:
        "hero"
        "features"
        "gallery";
    gap: 2rem;
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

.hero {
    grid-area: hero;
    text-align: center;
    padding: 4rem 2rem;
    background-color: #f4f4f4;
    border-radius: 8px;
}

.hero h1 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
}

.cta-button {
    padding: 0.8rem 1.5rem;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
    transition: background-color 0.3s;
}

.cta-button:hover {
    background-color: #2980b9;
}


.features {
    grid-area: features;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    justify-content: space-between;
}

.feature-card {
    flex: 1 1 300px;
    padding: 1.5rem;
    background-color: white;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.feature-card h2 {
    margin-bottom: 1rem;
    color: #2c3e50;
}


.gallery {
    grid-area: gallery;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 1rem;
}

.gallery-item {
    background-color: #3498db;
    color: white;
    padding: 2rem;
    text-align: center;
    border-radius: 8px;
    min-height: 150px;
    display: flex;
    align-items: center;
    justify-content: center;
}


footer {
    text-align: center;
    padding: 1.5rem;
    background-color: #2c3e50;
    color: white;
}


@media screen and (max-width: 768px) {
    .nav-links {
        position: absolute;
        right: 0;
        top: 70px;
        background-color: #2c3e50;
        flex-direction: column;
        width: 50%;
        height: calc(100vh - 70px);
        align-items: center;
        justify-content: space-evenly;
        transform: translateX(100%);
        transition: transform 0.5s ease-in;
    }

    .nav-links.active {
        transform: translateX(0);
    }

    .burger {
        display: block;
    }

    .hero h1 {
        font-size: 2rem;
    }

    .features {
        flex-direction: column;
    }

    .feature-card {
        flex: 1 1 auto;
    }
}


@media screen and (max-width: 480px) {
    .navbar {
        padding: 1rem;
    }

    .hero {
        padding: 2rem 1rem;
    }

    .hero h1 {
        font-size: 1.8rem;
    }

    .gallery {
        grid-template-columns: 1fr;
    }
}


.toggle .line1 {
    transform: rotate(-45deg) translate(-5px, 6px);
}
.toggle .line2 {
    opacity: 0;
}
.toggle .line3 {
    transform: rotate(45deg) translate(-5px, -6px);
}


## script.js

document.addEventListener('DOMContentLoaded', function() {
    const burger = document.querySelector('.burger');
    const navLinks = document.querySelector('.nav-links');
    
    burger.addEventListener('click', function() {

        navLinks.classList.toggle('active');
        

        burger.classList.toggle('toggle');
    });
});
