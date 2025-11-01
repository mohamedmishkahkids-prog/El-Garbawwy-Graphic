# El-Garbawwy-Graphic
 El-Gharbawwy Graphic – Professional Graphic Designer specializing in logos, branding, and creative visual identity. We help businesses stand out with modern, eye-catching designs that reflect their vision and values.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>El-Gharbawy Graphic - Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary-blue: #0d47a1;
            --light-blue: #1976d2;
            --yellow-accent: #ffeb3b;
            --light-grey: #f0f0f0;
            --white: #ffffff;
            --text-color: #333;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--white);
            overflow-x: hidden; /* Prevent horizontal scroll from animations */
        }

        /* --- Animations --- */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes zoomIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        .animate-fadeIn { animation: fadeIn 1s ease-out forwards; }
        .animate-fadeInUp { animation: fadeInUp 0.8s ease-out forwards; }
        .animate-slideUp { animation: slideUp 0.8s ease-out forwards; }
        .animate-zoomIn { animation: zoomIn 0.8s ease-out forwards; }
        .animate-pulse { animation: pulse 2s infinite ease-in-out; }
        .animate-bounce { animation: bounce 1s infinite; }


        /* --- Header --- */
        .header {
            background: linear-gradient(90deg, var(--primary-blue) 0%, var(--light-blue) 100%);
            color: var(--white);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            animation: fadeIn 1s ease-out forwards;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .header-content h1 {
            font-size: 2.2rem;
            font-weight: 700;
            animation: pulse 2s infinite ease-in-out;
        }

        .header-content nav ul {
            list-style: none;
            display: flex;
        }

        .header-content nav ul li {
            margin-left: 30px;
        }

        .header-content nav ul li a {
            color: var(--white);
            text-decoration: none;
            font-size: 1.1rem;
            font-weight: 600;
            position: relative;
            transition: color 0.3s ease;
        }

        .header-content nav ul li a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 3px;
            background-color: var(--yellow-accent);
            left: 0;
            bottom: -5px;
            transition: width 0.3s ease-in-out;
        }

        .header-content nav ul li a:hover::after {
            width: 100%;
        }
        .header-content nav ul li a:hover {
             color: var(--yellow-accent);
        }

        /* --- Hero Section (Implicit from About) --- */
        .hero {
            position: relative;
            height: 70vh; /* Make it more prominent */
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            overflow: hidden;
            padding: 20px;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1587614382346-4ec70e388b28?auto=format&fit=crop&w=1500&q=80') no-repeat center center/cover;
            filter: grayscale(50%) blur(2px); /* Subtle blur for effect */
            z-index: -2;
        }

        .hero::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6); /* Semi-transparent black overlay */
            z-index: -1;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            opacity: 0;
            animation: fadeInUp 1s ease-out forwards 0.5s; /* Delay for header */
        }

        .hero-content h2 {
            font-size: 3.5rem;
            margin-bottom: 15px;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .hero-content p {
            font-size: 1.3rem;
            line-height: 1.8;
            font-weight: 300;
        }

        /* --- Sections General Style --- */
        .section {
            padding: 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
            opacity: 0; /* Hidden by default, animated by JS */
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        .section.active {
            opacity: 1;
            transform: translateY(0);
        }

        .section h2 {
            font-size: 3rem;
            margin-bottom: 40px;
            font-weight: 700;
            color: var(--primary-blue);
            position: relative;
            display: inline-block;
        }

        .section h2::after {
            content: '';
            position: absolute;
            width: 70%;
            height: 4px;
            background-color: var(--yellow-accent);
            left: 15%;
            bottom: -10px;
            border-radius: 2px;
        }

        /* --- Projects Section --- */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .project-card {
            background-color: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-align: left;
            opacity: 0; /* Hidden by default, animated by JS */
            transform: scale(0.9);
            animation: zoomIn 0.6s ease-out forwards;
        }

        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .project-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .project-card:hover img {
            transform: scale(1.05);
        }

        .project-card-content {
            padding: 20px;
        }

        .project-card-content h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--primary-blue);
        }

        .project-card-content p {
            font-size: 0.95rem;
            color: #666;
        }

        /* --- Contact Section --- */
        .contact-content p {
            font-size: 1.2rem;
            margin-bottom: 40px;
            color: #555;
        }

        .whatsapp-button {
            display: inline-flex;
            align-items: center;
            background-color: #25d366; /* WhatsApp green */
            color: var(--white);
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-size: 1.2rem;
            font-weight: 600;
            transition: transform 0.3s ease, background-color 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        /* Changed to match prompt color for bounce */
        .whatsapp-button.animate-bounce {
             background-color: var(--yellow-accent);
             color: var(--primary-blue); /* Text color for yellow button */
             box-shadow: 0 5px 15px rgba(255, 235, 59, 0.4);
        }

        .whatsapp-button i {
            margin-right: 10px;
            font-size: 1.5rem;
        }

        .whatsapp-button:hover {
            transform: translateY(-5px);
            background-color: #128c7e; /* Darker WhatsApp green on hover */
        }

        /* --- Footer --- */
        .footer {
            background-color: var(--primary-blue);
            color: var(--white);
            text-align: center;
            padding: 25px 20px;
            font-size: 0.9rem;
            opacity: 0;
            animation: fadeIn 1s ease-out forwards 0.5s;
        }

        /* --- Responsive Design --- */
        @media (max-width: 900px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }

            .header-content h1 {
                margin-bottom: 15px;
            }

            .header-content nav ul {
                padding: 10px 0;
                flex-wrap: wrap;
                justify-content: center;
            }

            .header-content nav ul li {
                margin: 0 15px 10px;
            }

            .hero-content h2 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1rem;
            }

            .section {
                padding: 60px 15px;
            }

            .section h2 {
                font-size: 2.5rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .whatsapp-button {
                padding: 12px 25px;
                font-size: 1.1rem;
            }
        }

        @media (max-width: 600px) {
            .header-content h1 {
                font-size: 1.8rem;
            }

            .header-content nav ul li {
                margin: 0 10px 10px;
            }

            .hero-content h2 {
                font-size: 2rem;
            }

            .hero-content p {
                font-size: 0.9rem;
            }

            .section h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <header class="header">
        <div class="header-content">
            <h1>El-Gharbawy Graphic</h1>
            <nav>
                <ul>
                    <li><a href="#about">About</a></li>
                    <li><a href="#projects">Recent Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section id="about" class="hero">
        <div class="hero-content">
            <h2>About Us</h2>
            <p>We create stunning visuals that bring your ideas to life — from branding to social media design, motion graphics, and beyond.</p>
        </div>
    </section>

    <section id="projects" class="section">
        <h2>Recent Projects</h2>
        <div class="projects-grid">
            <div class="project-card animate-zoomIn" style="animation-delay: 0.2s;">
                <img src="https://images.unsplash.com/photo-1607083206968-13611e3b0f35?auto=format&fit=crop&w=800&q=80" alt="Brand Identity Design">
                <div class="project-card-content">
                    <h3>Brand Identity Design</h3>
                    <p>Crafting unique and memorable brand identities that resonate with your audience and leave a lasting impression.</p>
                </div>
            </div>
            <div class="project-card animate-zoomIn" style="animation-delay: 0.4s;">
                <img src="https://images.unsplash.com/photo-1559028012-481c04fa702d?auto=format&fit=crop&w=800&q=80" alt="Social Media Campaign">
                <div class="project-card-content">
                    <h3>Social Media Campaign</h3>
                    <p>Engaging visual content and strategies to boost your online presence and connect with your followers.</p>
                </div>
            </div>
            <div class="project-card animate-zoomIn" style="animation-delay: 0.6s;">
                <img src="https://images.unsplash.com/photo-1581093588401-22c3f85c03b3?auto=format&fit=crop&w=800&q=80" alt="Motion Graphic Promo">
                <div class="project-card-content">
                    <h3>Motion Graphic Promo</h3>
                    <p>Dynamic and captivating motion graphics to tell your story, promote your product, or explain complex ideas.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <h2>Contact Us</h2>
        <div class="contact-content">
            <p>Get in touch and let’s create something amazing together!</p>
            <a href="https://wa.me/201100258950" target="_blank" class="whatsapp-button animate-bounce">
                <i class="fab fa-whatsapp"></i> WhatsApp
            </a>
        </div>
    </section>

    <footer class="footer">
        <p>© 2025 El-Gharbawy Graphic | All Rights Reserved</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('.section');
            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.2
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                        observer.unobserve(entry.target); // Stop observing once animated
                    }
                });
            }, observerOptions);

            sections.forEach(section => {
                observer.observe(section);
            });

            // Specific animation for project cards within projects section
            const projectCards = document.querySelectorAll('.project-card');
            const projectObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'scale(1)';
                        observer.unobserve(entry.target);
                    }
                });
            }, {
                root: null,
                rootMargin: '0px',
                threshold: 0.1
            });

            projectCards.forEach(card => {
                projectObserver.observe(card);
            });

            // Ensure header animation runs
            document.querySelector('.header').style.animation = 'fadeIn 1s ease-out forwards';
            document.querySelector('.hero-content').style.animation = 'fadeInUp 1s ease-out forwards 0.5s';
        });
    </script>
</body>
</html>
