<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thiru Yatra - South Indian Spiritual & Cultural Tours</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --saffron: #FF9933;
            --deep-red: #C41E3A;
            --temple-gold: #D4AF37;
            --verdant-green: #228B22;
            --ocean-blue: #006994;
            --cream: #FFF8DC;
            --dark-charcoal: #2C3E50;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--cream);
            color: var(--dark-charcoal);
            overflow-x: hidden;
        }

        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }

        /* Animated Kolam Pattern Background */
        .kolam-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(255,153,51,0.03) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(196,30,58,0.03) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(212,175,55,0.03) 0%, transparent 50%);
            pointer-events: none;
            z-index: -1;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: linear-gradient(135deg, var(--saffron) 0%, #FF8000 100%);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            color: white;
            font-size: 1.8rem;
            font-weight: 700;
            text-decoration: none;
            font-family: 'Playfair Display', serif;
        }

        .logo::before {
            content: "🛕";
            font-size: 2rem;
            filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.3));
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: white;
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section with Temple Silhouette */
        .hero {
            margin-top: 80px;
            height: 100vh;
            background: linear-gradient(135deg, rgba(255,153,51,0.9) 0%, rgba(196,30,58,0.8) 100%),
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><path d="M0,500 Q300,400 600,450 T1200,400 L1200,600 L0,600 Z" fill="%23FFF8DC" opacity="0.1"/><path d="M100,500 L150,300 L200,500 Z" fill="%23D4AF37" opacity="0.3"/><path d="M900,500 L950,250 L1000,500 Z" fill="%23D4AF37" opacity="0.3"/></svg>');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="40" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="0.5"/></svg>');
            background-size: 100px;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-50px) rotate(360deg); }
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.3);
            animation: fadeInUp 1s ease-out;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.95;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 3rem;
            background: var(--temple-gold);
            color: var(--dark-charcoal);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            animation: fadeInUp 1s ease-out 0.6s both;
            border: 3px solid transparent;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
            background: transparent;
            color: white;
            border-color: white;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Section Styling */
        section {
            padding: 5rem 5%;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            color: var(--deep-red);
            margin-bottom: 3rem;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--saffron), var(--temple-gold));
            margin: 1rem auto;
            border-radius: 2px;
        }

        /* Destinations Grid */
        .destinations {
            background: white;
        }

        .destinations-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .destination-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s;
            position: relative;
            border: 2px solid transparent;
        }

        .destination-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
            border-color: var(--saffron);
        }

        .card-image {
            height: 250px;
            background: linear-gradient(135deg, var(--verdant-green) 0%, var(--ocean-blue) 100%);
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
        }

        .card-content {
            padding: 1.5rem;
        }

        .card-content h3 {
            color: var(--deep-red);
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .card-content p {
            color: #666;
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .price-tag {
            display: inline-block;
            background: var(--saffron);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-weight: 600;
        }

        /* Services Section with Icons */
        .services {
            background: linear-gradient(135deg, var(--cream) 0%, #fff 100%);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            max-width: 1000px;
            margin: 0 auto;
        }

        .service-item {
            text-align: center;
            padding: 2rem;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.05);
            transition: all 0.3s;
            border-top: 4px solid var(--temple-gold);
        }

        .service-item:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }

        .service-item h3 {
            color: var(--dark-charcoal);
            margin-bottom: 0.5rem;
        }

        /* Itinerary Section */
        .itinerary {
            background: var(--dark-charcoal);
            color: white;
            position: relative;
            overflow: hidden;
        }

        .itinerary::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(255,153,51,0.1) 0%, transparent 70%);
            border-radius: 50%;
        }

        .timeline {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(to bottom, var(--saffron), var(--temple-gold));
            transform: translateX(-50%);
        }

        .timeline-item {
            display: flex;
            justify-content: flex-end;
            padding-right: 50%;
            position: relative;
            margin-bottom: 3rem;
        }

        .timeline-item:nth-child(even) {
            justify-content: flex-start;
            padding-right: 0;
            padding-left: 50%;
        }

        .timeline-content {
            background: rgba(255,255,255,0.1);
            padding: 1.5rem;
            border-radius: 15px;
            width: 80%;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.2);
        }

        .timeline-dot {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 20px;
            height: 20px;
            background: var(--temple-gold);
            border-radius: 50%;
            border: 4px solid var(--dark-charcoal);
        }

        /* Testimonials */
        .testimonials {
            background: white;
        }

        .testimonial-carousel {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .testimonial-card {
            background: linear-gradient(135deg, var(--cream) 0%, white 100%);
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border-left: 5px solid var(--saffron);
            margin: 1rem;
        }

        .testimonial-text {
            font-size: 1.2rem;
            font-style: italic;
            color: #555;
            margin-bottom: 1.5rem;
            line-height: 1.8;
        }

        .testimonial-author {
            color: var(--deep-red);
            font-weight: 600;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(135deg, var(--saffron) 0%, var(--deep-red) 100%);
            color: white;
            position: relative;
        }

        .contact-container {
            max-width: 1000px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
        }

        .contact-info h3 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
        }

        .contact-detail {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .contact-form {
            background: rgba(255,255,255,0.15);
            padding: 2rem;
            border-radius: 20px;
            backdrop-filter: blur(10px);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: none;
            border-radius: 10px;
            background: rgba(255,255,255,0.9);
            font-family: 'Poppins', sans-serif;
        }

        .form-group textarea {
            resize: vertical;
            min-height: 100px;
        }

        .submit-btn {
            width: 100%;
            padding: 1rem;
            background: var(--temple-gold);
            color: var(--dark-charcoal);
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .submit-btn:hover {
            background: white;
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: var(--dark-charcoal);
            color: white;
            text-align: center;
            padding: 2rem;
            border-top: 5px solid var(--saffron);
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
            margin-bottom: 2rem;
        }

        .footer-section h4 {
            color: var(--temple-gold);
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }

        .footer-section a {
            color: #aaa;
            text-decoration: none;
            display: block;
            margin-bottom: 0.5rem;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--saffron);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: var(--saffron);
            transform: translateY(-3px);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .mobile-menu {
                display: block;
            }
            
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .timeline::before {
                left: 20px;
            }
            
            .timeline-item,
            .timeline-item:nth-child(even) {
                padding-left: 50px;
                padding-right: 0;
                justify-content: flex-start;
            }
            
            .timeline-dot {
                left: 20px;
            }
        }

        /* Loading Animation */
        .loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--cream);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            transition: opacity 0.5s;
        }

        .loader.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .spinner {
            width: 60px;
            height: 60px;
            border: 4px solid var(--saffron);
            border-top-color: transparent;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loader" id="loader">
        <div class="spinner"></div>
    </div>

    <!-- Kolam Background Pattern -->
    <div class="kolam-bg"></div>

    <!-- Navigation -->
    <nav>
        <a href="#" class="logo">Thiru Yatra</a>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#destinations">Destinations</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#itinerary">Itinerary</a></li>
            <li><a href="#testimonials">Reviews</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <div class="mobile-menu">☰</div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Discover Sacred South India</h1>
            <p>Journey through ancient temples, serene backwaters, and misty hill stations</p>
            <a href="#destinations" class="cta-button">Begin Your Yatra</a>
        </div>
    </section>

    <!-- Destinations Section -->
    <section class="destinations" id="destinations">
        <h2 class="section-title">Sacred Destinations</h2>
        <div class="destinations-grid">
            <div class="destination-card">
                <div class="card-image">🛕</div>
                <div class="card-content">
                    <h3>Tamil Nadu Temple Circuit</h3>
                    <p>Explore the magnificent Dravidian architecture of Madurai, Tanjore, and Rameswaram. Witness ancient rituals and intricate carvings.</p>
                    <span class="price-tag">₹25,000 / 5 Days</span>
                </div>
            </div>
            
            <div class="destination-card">
                <div class="card-image" style="background: linear-gradient(135deg, #006994 0%, #228B22 100%);">🚣</div>
                <div class="card-content">
                    <h3>Kerala Backwaters</h3>
                    <p>Glide through the tranquil backwaters of Alleppey in traditional houseboats. Experience Ayurvedic wellness and coastal cuisine.</p>
                    <span class="price-tag">₹18,000 / 4 Days</span>
                </div>
            </div>
            
            <div class="destination-card">
                <div class="card-image" style="background: linear-gradient(135deg, #8B4513 0%, #D2691E 100%);">🌄</div>
                <div class="card-content">
                    <h3>Karnataka Heritage</h3>
                    <p>Discover the ruins of Hampi, palaces of Mysore, and coffee plantations of Coorg. A blend of history and nature.</p>
                    <span class="price-tag">₹22,000 / 6 Days</span>
                </div>
            </div>
            
            <div class="destination-card">
                <div class="card-image" style="background: linear-gradient(135deg, #4B0082 0%, #8A2BE2 100%);">🏔️</div>
                <div class="card-content">
                    <h3>Andhra Pradesh Pilgrimage</h3>
                    <p>Visit Tirupati Balaji, ancient Buddhist sites at Amaravati, and the pristine beaches of Visakhapatnam.</p>
                    <span class="price-tag">₹15,000 / 3 Days</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <h2 class="section-title">Our Services</h2>
        <div class="services-grid">
            <div class="service-item">
                <span class="service-icon">🚗</span>
                <h3>Private Transport</h3>
                <p>AC vehicles with experienced drivers familiar with temple routes and rituals</p>
            </div>
            <div class="service-item">
                <span class="service-icon">🏨</span>
                <h3>Heritage Stays</h3>
                <p>Carefully selected hotels and traditional homestays near temple complexes</p>
            </div>
            <div class="service-item">
                <span class="service-icon">🍛</span>
                <h3>Sattvic Meals</h3>
                <p>Authentic South Indian vegetarian cuisine prepared according to temple traditions</p>
            </div>
            <div class="service-item">
                <span class="service-icon">🙏</span>
                <h3>Priest Services</h3>
                <p>Special darshan arrangements and puja services at major temples</p>
            </div>
        </div>
    </section>

    <!-- Itinerary Section -->
    <section class="itinerary" id="itinerary">
        <h2 class="section-title" style="color: white;">Sample Itinerary</h2>
        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-content">
                    <h3>Day 1: Arrival & Chennai</h3>
                    <p>Welcome at Chennai airport. Visit Kapaleeshwarar Temple and Marina Beach. Traditional South Indian dinner.</p>
                </div>
                <div class="timeline-dot"></div>
            </div>
            
            <div class="timeline-item">
                <div class="timeline-content">
                    <h3>Day 2: Kanchipuram</h3>
                    <p>Visit the city of thousand temples. Silk weaving demonstration and Ekambareswarar Temple darshan.</p>
                </div>
                <div class="timeline-dot"></div>
            </div>
            
            <div class="timeline-item">
                <div class="timeline-content">
                    <h3>Day 3: Pondicherry</h3>
                    <p>French colonial architecture, Auroville meditation center, and coastal temple visits.</p>
                </div>
                <div class="timeline-dot"></div>
            </div>
            
            <div class="timeline-item">
                <div class="timeline-content">
                    <h3>Day 4: Tanjore & Trichy</h3>
                    <p>Brihadeeswarar Temple (UNESCO site) and Rock Fort Temple. Evening classical dance performance.</p>
                </div>
                <div class="timeline-dot"></div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials" id="testimonials">
        <h2 class="section-title">Traveler Experiences</h2>
        <div class="testimonial-carousel">
            <div class="testimonial-card">
                <p class="testimonial-text">"The attention to detail in planning our temple visits was remarkable. We got to participate in rituals that regular tourists miss. Truly a spiritual journey!"</p>
                <p class="testimonial-author">- Lakshmi & Family, Bangalore</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="contact-container">
            <div class="contact-info">
                <h3>Begin Your Sacred Journey</h3>
                <p style="margin-bottom: 2rem; opacity: 0.9;">Let us craft your perfect South Indian pilgrimage experience</p>
                
                <div class="contact-detail">
                    <span>📍</span>
                    <span>123 Temple Street, Mylapore, Chennai - 600004</span>
                </div>
                <div class="contact-detail">
                    <span>📞</span>
                    <span>+91 44 2345 6789</span>
                </div>
                <div class="contact-detail">
                    <span>✉️</span>
                    <span>yatra@thiruyatra.com</span>
                </div>
                <div class="contact-detail">
                    <span>🕉️</span>
                    <span>WhatsApp: +91 98765 43210</span>
                </div>
            </div>
            
            <div class="contact-form">
                <form id="bookingForm">
                    <div class="form-group">
                        <label>Your Name</label>
                        <input type="text" required placeholder="Enter your full name">
                    </div>
                    <div class="form-group">
                        <label>Email Address</label>
                        <input type="email" required placeholder="your@email.com">
                    </div>
                    <div class="form-group">
                        <label>Phone Number</label>
                        <input type="tel" placeholder="+91 98765 43210">
                    </div>
                    <div class="form-group">
                        <label>Select Package</label>
                        <select required>
                            <option value="">Choose your yatra...</option>
                            <option value="tamil">Tamil Nadu Temple Circuit</option>
                            <option value="kerala">Kerala Backwaters</option>
                            <option value="karnataka">Karnataka Heritage</option>
                            <option value="andhra">Andhra Pilgrimage</option>
                            <option value="custom">Custom Itinerary</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Special Requirements</label>
                        <textarea placeholder="Dietary restrictions, mobility assistance, specific temples..."></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Request Booking</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h4>Thiru Yatra</h4>
                <p>Authentic South Indian spiritual journeys since 2010. We specialize in temple tours, cultural experiences, and pilgrimage arrangements.</p>
                <div class="social-links">
                    <a href="#">f</a>
                    <a href="#">📷</a>
                    <a href="#">🐦</a>
                    <a href="#">▶️</a>
                </div>
            </div>
            <div class="footer-section">
                <h4>Quick Links</h4>
                <a href="#destinations">Destinations</a>
                <a href="#services">Services</a>
                <a href="#itinerary">Sample Itinerary</a>
                <a href="#contact">Contact Us</a>
                <a href="#">Blog</a>
            </div>
            <div class="footer-section">
                <h4>Support</h4>
                <a href="#">FAQ</a>
                <a href="#">Cancellation Policy</a>
                <a href="#">Terms & Conditions</a>
                <a href="#">Privacy Policy</a>
            </div>
            <div class="footer-section">
                <h4>Newsletter</h4>
                <p>Subscribe for festival dates and special tour offers</p>
                <form style="margin-top: 1rem;">
                    <input type="email" placeholder="Your email" style="padding: 0.5rem; border-radius: 5px; border: none; width: 100%; margin-bottom: 0.5rem;">
                    <button style="padding: 0.5rem 1rem; background: var(--saffron); color: white; border: none; border-radius: 5px; cursor: pointer; width: 100%;">Subscribe</button>
                </form>
            </div>
        </div>
        <p style="border-top: 1px solid #444; padding-top: 2rem; margin-top: 2rem; color: #888;">
            © 2025 Thiru Yatra Tours & Travels. All rights reserved. | Made with 🙏 in South India
        </p>
    </footer>

    <script>
        // Remove loader when page loads
        window.addEventListener('load', () => {
            setTimeout(() => {
                document.getElementById('loader').classList.add('hidden');
            }, 500);
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission handler
        document.getElementById('bookingForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Create custom styled alert
            const alert = document.createElement('div');
            alert.style.cssText = `
                position: fixed;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                background: white;
                padding: 2rem;
                border-radius: 20px;
                box-shadow: 0 20px 60px rgba(0,0,0,0.3);
                z-index: 10000;
                text-align: center;
                border: 3px solid var(--saffron);
                max-width: 400px;
            `;
            alert.innerHTML = `
                <div style="font-size: 3rem; margin-bottom: 1rem;">🙏</div>
                <h3 style="color: var(--deep-red); margin-bottom: 1rem;">Namaskaram!</h3>
                <p style="margin-bottom: 1.5rem;">Thank you for your inquiry. Our team will contact you within 24 hours to plan your sacred journey.</p>
                <button onclick="this.parentElement.remove()" style="padding: 0.8rem 2rem; background: var(--saffron); color: white; border: none; border-radius: 25px; cursor: pointer; font-weight: 600;">Close</button>
            `;
            document.body.appendChild(alert);
            
            this.reset();
        });

        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if (window.scrollY > 100) {
                nav.style.background = 'rgba(255, 153, 51, 0.95)';
                nav.style.backdropFilter = 'blur(10px)';
            } else {
                nav.style.background = 'linear-gradient(135deg, var(--saffron) 0%, #FF8000 100%)';
                nav.style.backdropFilter = 'none';
            }
        });

        // Mobile menu toggle
        document.querySelector('.mobile-menu').addEventListener('click', function() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
            navLinks.style.position = 'absolute';
            navLinks.style.top = '100%';
            navLinks.style.left = '0';
            navLinks.style.right = '0';
            navLinks.style.background = 'var(--saffron)';
            navLinks.style.flexDirection = 'column';
            navLinks.style.padding = '1rem';
        });

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe all cards
        document.querySelectorAll('.destination-card, .service-item, .timeline-item').forEach((el) => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease-out';
            observer.observe(el);
        });
    </script>
</body>
</html>
