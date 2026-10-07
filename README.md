<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <meta name="description" content="Personal website and portfolio">
    <meta name="author" content="Your Name">

    <title>Your Name | Personal Website</title>

    <!-- Google Font -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link
        href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@500;600;700&display=swap"
        rel="stylesheet"
    >

    <!-- Main CSS -->
    <link rel="stylesheet" href="style.css">
</head>

<body>

    <!-- =========================
         NAVIGATION
    ========================== -->
    <header class="site-header">
        <nav class="navbar container">

            <!-- Change your name here -->
            <a href="index.html" class="logo">
                Your<span>Name</span>
            </a>

            <!-- Mobile menu button -->
            <button
                class="menu-toggle"
                aria-label="Open navigation menu"
                aria-expanded="false"
            >
                <span></span>
                <span></span>
                <span></span>
            </button>

            <ul class="nav-links">
                <li><a href="index.html" class="active">Home</a></li>
                <li><a href="gallery.html">Gallery</a></li>
                <li><a href="blog.html">Blog</a></li>
                <li><a href="about.html">About</a></li>
            </ul>

        </nav>
    </header>


    <main>

        <!-- =========================
             HERO SECTION
        ========================== -->
        <section class="hero">

            <div class="hero-content container">

                <div class="hero-text">

                    <p class="eyebrow">
                        Welcome to my website
                    </p>

                    <!-- Change your name -->
                    <h1>
                        Hello, I'm
                        <span>Your Name</span>
                    </h1>

                    <!-- Change your tagline -->
                    <p class="hero-description">
                        A creative individual exploring ideas, photography,
                        design, technology, and everything that inspires me.
                    </p>

                    <div class="hero-buttons">
                        <a href="gallery.html" class="btn btn-primary">
                            Explore My Work
                        </a>

                        <a href="about.html" class="btn btn-secondary">
                            About Me
                        </a>
                    </div>

                </div>

                <div class="hero-image">
                    <img
                        src="https://images.unsplash.com/photo-1497366811353-6870744d04b2?auto=format&fit=crop&w=1000&q=85"
                        alt="Modern creative workspace"
                    >
                </div>

            </div>

        </section>


        <!-- =========================
             INTRODUCTION
        ========================== -->
        <section class="section">

            <div class="container narrow">

                <div class="section-heading center">

                    <p class="eyebrow">
                        A little about me
                    </p>

                    <h2>
                        Creating, learning & exploring.
                    </h2>

                    <p>
                        This website is a place where I share my work,
                        thoughts, projects, photographs, and things I find
                        interesting.
                    </p>

                </div>

            </div>

        </section>


        <!-- =========================
             FEATURED WORK
        ========================== -->
        <section class="section section-soft">

            <div class="container">

                <div class="section-heading">

                    <div>
                        <p class="eyebrow">Featured</p>

                        <h2>
                            Selected work
                        </h2>
                    </div>

                    <a href="gallery.html" class="text-link">
                        View gallery →
                    </a>

                </div>


                <div class="featured-grid">

                    <article class="featured-card">
                        <img
                            src="https://images.unsplash.com/photo-1518005020951-eccb494ad742?auto=format&fit=crop&w=900&q=85"
                            alt="Architecture project"
                            loading="lazy"
                        >

                        <div class="featured-info">
                            <span>Projects</span>
                            <h3>Modern Spaces</h3>
                        </div>
                    </article>


                    <article class="featured-card">
                        <img
                            src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=900&q=85"
                            alt="Creative photography"
                            loading="lazy"
                        >

                        <div class="featured-info">
                            <span>Photography</span>
                            <h3>Visual Stories</h3>
                        </div>
                    </article>


                    <article class="featured-card">
                        <img
                            src="https://images.unsplash.com/photo-1549490349-8643362247b5?auto=format&fit=crop&w=900&q=85"
                            alt="Colorful artwork"
                            loading="lazy"
                        >

                        <div class="featured-info">
                            <span>Art</span>
                            <h3>Color & Form</h3>
                        </div>
                    </article>

                </div>

            </div>

        </section>


        <!-- =========================
             CALL TO ACTION
        ========================== -->
        <section class="cta-section">

            <div class="container narrow center">

                <p class="eyebrow">
                    Let's connect
                </p>

                <h2>
                    Have an idea or just want to say hello?
                </h2>

                <p>
                    I'd love to hear from you.
                </p>

                <a href="about.html#contact" class="btn btn-light">
                    Get in touch
                </a>

            </div>

        </section>

    </main>


    <!-- =========================
         FOOTER
    ========================== -->
    <footer class="site-footer">

        <div class="container footer-content">

            <div>
                <a href="index.html" class="logo footer-logo">
                    Your<span>Name</span>
                </a>

                <p>
                    Creating things and enjoying the journey.
                </p>
            </div>


            <div class="footer-socials">

                <!-- Replace these links with your real profiles -->
                <a href="#" aria-label="Instagram">Instagram</a>
                <a href="#" aria-label="Twitter">X</a>
                <a href="#" aria-label="LinkedIn">LinkedIn</a>
                <a href="#" aria-label="YouTube">YouTube</a>

            </div>

        </div>


        <div class="container copyright">

            <p>
                © <span id="year"></span> Your Name. All rights reserved.
            </p>

        </div>

    </footer>


    <!-- JavaScript -->
    <script src="script.js"></script>

</body>
</html>