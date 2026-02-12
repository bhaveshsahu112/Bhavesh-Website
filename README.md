<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Avighna — Crafted for Those Who Lead</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700;900&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --white: #FFFFFF;
            --off-white: #FAFAFA;
            --light-grey: #F5F5F5;
            --mid-grey: #E0E0E0;
            --text-grey: #666666;
            --black: #0A0A0A;
            --accent: #1A1A1A;
        }

        body {
            font-family: 'DM Sans', sans-serif;
            background: var(--white);
            color: var(--black);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            padding: 1.5rem 6%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            border-bottom: 1px solid var(--mid-grey);
            animation: slideDown 0.6s ease;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 2px;
            color: var(--black);
        }

        .nav-links {
            display: flex;
            gap: 3rem;
            list-style: none;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--black);
            font-weight: 500;
            font-size: 0.95rem;
            letter-spacing: 0.5px;
            transition: all 0.3s ease;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 1px;
            background: var(--black);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .cart-btn {
            background: var(--black);
            color: var(--white);
            padding: 0.7rem 1.8rem;
            border: none;
            font-weight: 600;
            font-size: 0.9rem;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
        }

        .cart-btn:hover {
            background: var(--accent);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            margin-top: 80px;
            padding: 10rem 6% 8rem;
            background: var(--white);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(0,0,0,0.02) 0%, transparent 70%);
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            50% { transform: translate(-50px, -50px) rotate(180deg); }
        }

        .hero-content {
            max-width: 900px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .hero-label {
            font-size: 0.85rem;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: var(--text-grey);
            margin-bottom: 2rem;
            font-weight: 500;
            animation: fadeIn 0.8s ease 0.2s both;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 5.5rem;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 2rem;
            color: var(--black);
            animation: fadeIn 0.8s ease 0.4s both;
        }

        .hero-subtitle {
            font-size: 1.4rem;
            color: var(--text-grey);
            margin-bottom: 1.5rem;
            font-weight: 400;
            line-height: 1.8;
            animation: fadeIn 0.8s ease 0.6s both;
        }

        .hero-punch {
            font-size: 1.1rem;
            color: var(--black);
            margin-bottom: 3rem;
            font-weight: 600;
            font-style: italic;
            animation: fadeIn 0.8s ease 0.8s both;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .cta-primary {
            display: inline-block;
            background: var(--black);
            color: var(--white);
            padding: 1.3rem 3.5rem;
            text-decoration: none;
            font-weight: 700;
            font-size: 1rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            transition: all 0.4s ease;
            border: 2px solid var(--black);
            animation: fadeIn 0.8s ease 1s both;
        }

        .cta-primary:hover {
            background: var(--white);
            color: var(--black);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        /* Features Bar */
        .features-bar {
            background: var(--light-grey);
            padding: 2.5rem 6%;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 2rem;
            border-top: 1px solid var(--mid-grey);
            border-bottom: 1px solid var(--mid-grey);
        }

        .feature {
            text-align: center;
            padding: 1rem;
        }

        .feature-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
            display: block;
        }

        .feature h3 {
            font-size: 0.95rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .feature p {
            font-size: 0.9rem;
            color: var(--text-grey);
        }

        /* Section Base */
        section {
            padding: 8rem 6%;
        }

        .section-header {
            text-align: center;
            margin-bottom: 6rem;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .section-label {
            font-size: 0.8rem;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: var(--text-grey);
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .section-title {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: var(--black);
            line-height: 1.2;
        }

        .section-punch {
            font-size: 1.2rem;
            color: var(--text-grey);
            font-style: italic;
            font-weight: 500;
        }

        /* Product Grid */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 3rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-card {
            background: var(--white);
            border: 1px solid var(--mid-grey);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.08);
            border-color: var(--black);
        }

        .product-image-wrapper {
            width: 100%;
            height: 420px;
            background: var(--light-grey);
            position: relative;
            overflow: hidden;
        }

        .product-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .product-card:hover .product-image {
            transform: scale(1.05);
        }

        .product-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--black);
            color: var(--white);
            padding: 0.5rem 1.2rem;
            font-size: 0.7rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .product-info {
            padding: 2rem;
            background: var(--white);
        }

        .product-category {
            font-size: 0.75rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            color: var(--text-grey);
            margin-bottom: 0.8rem;
            font-weight: 600;
        }

        .product-name {
            font-family: 'Playfair Display', serif;
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 0.8rem;
            color: var(--black);
        }

        .product-tagline {
            font-size: 0.95rem;
            color: var(--text-grey);
            margin-bottom: 1.5rem;
            line-height: 1.6;
            font-style: italic;
        }

        .product-price {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--black);
            margin-bottom: 1.5rem;
        }

        .product-btn {
            width: 100%;
            background: transparent;
            color: var(--black);
            border: 2px solid var(--black);
            padding: 1rem;
            font-weight: 700;
            font-size: 0.85rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .product-btn:hover {
            background: var(--black);
            color: var(--white);
        }

        /* Enquiry Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.3s ease;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: var(--white);
            padding: 3rem;
            max-width: 500px;
            width: 90%;
            position: relative;
            animation: slideUp 0.4s ease;
        }

        @keyframes slideUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .modal-close {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--black);
            transition: transform 0.3s ease;
        }

        .modal-close:hover {
            transform: rotate(90deg);
        }

        .modal h3 {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            margin-bottom: 0.5rem;
            color: var(--black);
        }

        .modal-product {
            font-size: 0.9rem;
            color: var(--text-grey);
            margin-bottom: 2rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--black);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid var(--mid-grey);
            background: var(--white);
            font-family: 'DM Sans', sans-serif;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--black);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 100px;
        }

        .submit-btn {
            width: 100%;
            background: var(--black);
            color: var(--white);
            border: 2px solid var(--black);
            padding: 1.2rem;
            font-weight: 700;
            font-size: 0.85rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            background: var(--white);
            color: var(--black);
        }

        .submit-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .success-message {
            display: none;
            text-align: center;
        }

        .success-message.active {
            display: block;
        }

        .success-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        .success-message h3 {
            margin-bottom: 1rem;
        }

        .success-message p {
            color: var(--text-grey);
            line-height: 1.8;
        }

        /* Alternating Section Backgrounds */
        #belts {
            background: var(--white);
        }

        #wallets {
            background: var(--off-white);
        }

        #caps {
            background: var(--white);
        }

        /* Manifesto Section */
        .manifesto {
            background: var(--black);
            color: var(--white);
            padding: 8rem 6%;
            text-align: center;
        }

        .manifesto-content {
            max-width: 900px;
            margin: 0 auto;
        }

        .manifesto h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 2rem;
            line-height: 1.2;
        }

        .manifesto p {
            font-size: 1.3rem;
            line-height: 1.9;
            margin-bottom: 1.5rem;
            color: rgba(255,255,255,0.9);
        }

        .manifesto-quote {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            font-style: italic;
            margin-top: 3rem;
            padding-top: 3rem;
            border-top: 1px solid rgba(255,255,255,0.2);
            color: var(--white);
        }

        /* Testimonials */
        .testimonials {
            background: var(--light-grey);
            padding: 8rem 6%;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .testimonial {
            background: var(--white);
            padding: 3rem;
            border: 1px solid var(--mid-grey);
            position: relative;
        }

        .quote-mark {
            font-family: 'Playfair Display', serif;
            font-size: 5rem;
            color: var(--mid-grey);
            line-height: 1;
            margin-bottom: 1rem;
        }

        .testimonial-text {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 2rem;
            color: var(--black);
        }

        .testimonial-author {
            font-weight: 700;
            color: var(--black);
            font-size: 0.95rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .testimonial-title {
            font-size: 0.85rem;
            color: var(--text-grey);
        }

        /* Newsletter */
        .newsletter {
            background: var(--white);
            padding: 8rem 6%;
            text-align: center;
            border-top: 1px solid var(--mid-grey);
            border-bottom: 1px solid var(--mid-grey);
        }

        .newsletter-content {
            max-width: 700px;
            margin: 0 auto;
        }

        .newsletter h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
        }

        .newsletter p {
            font-size: 1.2rem;
            color: var(--text-grey);
            margin-bottom: 3rem;
        }

        .newsletter-form {
            display: flex;
            gap: 1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .newsletter-input {
            flex: 1;
            padding: 1.2rem 1.5rem;
            border: 2px solid var(--mid-grey);
            background: var(--white);
            font-size: 1rem;
            font-family: 'DM Sans', sans-serif;
            transition: all 0.3s ease;
        }

        .newsletter-input:focus {
            outline: none;
            border-color: var(--black);
        }

        .newsletter-btn {
            background: var(--black);
            color: var(--white);
            padding: 1.2rem 3rem;
            border: 2px solid var(--black);
            font-weight: 700;
            font-size: 0.9rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .newsletter-btn:hover {
            background: var(--white);
            color: var(--black);
        }

        /* Footer */
        footer {
            background: var(--black);
            color: var(--white);
            padding: 5rem 6% 3rem;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 4rem;
            margin-bottom: 4rem;
        }

        .footer-brand h3 {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            margin-bottom: 1rem;
            letter-spacing: 2px;
        }

        .footer-brand p {
            color: rgba(255,255,255,0.7);
            line-height: 1.8;
        }

        .footer-section h4 {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            transition: color 0.3s ease;
            font-size: 0.95rem;
        }

        .footer-links a:hover {
            color: var(--white);
        }

        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.1);
            padding-top: 2rem;
            text-align: center;
            color: rgba(255,255,255,0.5);
            font-size: 0.9rem;
        }

        /* Responsive */
        @media (max-width: 968px) {
            .hero h1 {
                font-size: 3.5rem;
            }

            .section-title {
                font-size: 2.5rem;
            }

            .nav-links {
                display: none;
            }

            .features-bar {
                grid-template-columns: repeat(2, 1fr);
            }

            .footer-content {
                grid-template-columns: 1fr;
            }

            .newsletter-form {
                flex-direction: column;
            }

            .product-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="logo">Bhavesh</div>
        <ul class="nav-links">
            <li><a href="#belts">Belts</a></li>
            <li><a href="#wallets">Wallets</a></li>
            <li><a href="#caps">Caps</a></li>
            <li><a href="#story">Our Story</a></li>
        </ul>
        <button class="cart-btn">Cart (0)</button>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <p class="hero-label">Est. 2024 — Premium Accessories</p>
            <h1>Crafted for Those<br>Who Lead</h1>
            <p class="hero-subtitle">Where precision meets pride. Where quality transcends trends.<br>Where every detail declares your standard.</p>
            <p class="hero-punch">Because excellence isn't an option—it's your signature.</p>
            <a href="#belts" class="cta-primary">Discover Collection</a>
        </div>
    </section>

    <!-- Features Bar -->
    <div class="features-bar">
        <div class="feature">
            <span class="feature-icon">🎯</span>
            <h3>Precision Crafted</h3>
            <p>Every stitch matters</p>
        </div>
        <div class="feature">
            <span class="feature-icon">♾️</span>
            <h3>Built to Last</h3>
            <p>Lifetime quality guarantee</p>
        </div>
        <div class="feature">
            <span class="feature-icon">🚚</span>
            <h3>Free Shipping</h3>
            <p>On all orders above ₹999</p>
        </div>
        <div class="feature">
            <span class="feature-icon">🔒</span>
            <h3>Secure Payment</h3>
            <p>Your trust, protected</p>
        </div>
    </div>

    <!-- Belts Section -->
    <section id="belts">
        <div class="section-header">
            <p class="section-label">The Power Collection</p>
            <h2 class="section-title">Belts That Command Respect</h2>
            <p class="section-punch">Not just an accessory. A statement of intent.</p>
        </div>
        <div class="product-grid">
            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="C:\Users\DELL\Downloads\A7400541.JPG" alt="Executive Leather Belt" class="product-image">
                    <div class="product-badge">Bestseller</div>
                </div>
                <div class="product-info">
                    <p class="product-category">Premium Leather</p>
                    <h3 class="product-name">The Executive</h3>
                    <p class="product-tagline">Full-grain Italian leather. Handcrafted brass buckle. For the boardroom and beyond.</p>
                    <p class="product-price">₹2,499</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="C:\Users\DELL\Downloads\A7400541.JPG" alt="Cotton Casual Belt" class="product-image">
                </div>
                <div class="product-info">
                    <p class="product-category">Cotton Canvas</p>
                    <h3 class="product-name">The Navigator</h3>
                    <p class="product-tagline">Military-grade canvas. Weekend warrior approved. Effortless style, maximum comfort.</p>
                    <p class="product-price">₹1,299</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="C:\Users\DELL\Downloads\A7400541.JPG" alt="Women's Designer Belt" class="product-image">
                    <div class="product-badge">New Arrival</div>
                </div>
                <div class="product-info">
                    <p class="product-category">Women's Collection</p>
                    <h3 class="product-name">The Maven</h3>
                    <p class="product-tagline">Designed for women who define trends, not follow them. Elegance with edge.</p>
                    <p class="product-price">₹1,899</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="C:\Users\DELL\Downloads\A7400541.JPG" alt="Luxury Leather Belt" class="product-image">
                </div>
                <div class="product-info">
                    <p class="product-category">Luxury Edition</p>
                    <h3 class="product-name">The Chairman</h3>
                    <p class="product-tagline">Argentinian leather. Swiss craftsmanship. For those who settle for nothing less.</p>
                    <p class="product-price">₹3,999</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Wallets Section -->
    <section id="wallets">
        <div class="section-header">
            <p class="section-label">The Essentials</p>
            <h2 class="section-title">Wallets Worth Carrying</h2>
            <p class="section-punch">Slim profile. Bold statement. Your essentials, elevated.</p>
        </div>
        <div class="product-grid">
            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="C:\Users\DELL\Downloads\A7400541.JPG" alt="Premium Leather Wallet" class="product-image">
                    <div class="product-badge">Bestseller</div>
                </div>
                <div class="product-info">
                    <p class="product-category">Genuine Leather</p>
                    <h3 class="product-name">The Gentleman</h3>
                    <p class="product-tagline">Timeless design. Premium leather that ages like fine wine. Classic never looked better.</p>
                    <p class="product-price">₹1,799</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="C:\Users\DELL\Downloads\A7400541.JPG" alt="Minimalist Wallet" class="product-image">
                    <div class="product-badge">New Arrival</div>
                </div>
                <div class="product-info">
                    <p class="product-category">Gen-Z Edition</p>
                    <h3 class="product-name">The Minimalist</h3>
                    <p class="product-tagline">Less bulk. More swagger. RFID-protected. Built for the modern maverick.</p>
                    <p class="product-price">₹1,299</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1610824170934-c6ca3d39b76b?w=600&h=800&fit=crop" alt="RFID Wallet" class="product-image">
                </div>
                <div class="product-info">
                    <p class="product-category">RFID Protected</p>
                    <h3 class="product-name">The Guardian</h3>
                    <p class="product-tagline">Military-grade protection. Civilian sophistication. Your security, invisible.</p>
                    <p class="product-price">₹1,599</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1591348278863-da87043c2e4b?w=600&h=800&fit=crop" alt="Designer Wallet" class="product-image">
                </div>
                <div class="product-info">
                    <p class="product-category">Artisan Series</p>
                    <h3 class="product-name">The Connoisseur</h3>
                    <p class="product-tagline">Hand-stitched perfection. Limited edition craftsmanship. For those who appreciate art.</p>
                    <p class="product-price">₹2,999</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Caps Section -->
    <section id="caps">
        <div class="section-header">
            <p class="section-label">The Final Touch</p>
            <h2 class="section-title">Caps That Crown Glory</h2>
            <p class="section-punch">Top off your look. Own the spotlight.</p>
        </div>
        <div class="product-grid">
            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1588850561407-ed78c282e89b?w=600&h=800&fit=crop" alt="Cotton Cap" class="product-image">
                </div>
                <div class="product-info">
                    <p class="product-category">Cotton Classic</p>
                    <h3 class="product-name">The Street Legend</h3>
                    <p class="product-tagline">Premium cotton twill. Urban energy. Street credibility, premium quality.</p>
                    <p class="product-price">₹899</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1575428652377-a2d80e2277fc?w=600&h=800&fit=crop" alt="Parachute Cap" class="product-image">
                    <div class="product-badge">New Arrival</div>
                </div>
                <div class="product-info">
                    <p class="product-category">Tech Fabric</p>
                    <h3 class="product-name">The Aero</h3>
                    <p class="product-tagline">Parachute material. Feather-light. Future-forward design meets athletic comfort.</p>
                    <p class="product-price">₹1,099</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1589992260233-b25a3a4c54e7?w=600&h=800&fit=crop" alt="Snapback Cap" class="product-image">
                    <div class="product-badge">Bestseller</div>
                </div>
                <div class="product-info">
                    <p class="product-category">Snapback</p>
                    <h3 class="product-name">The Game Changer</h3>
                    <p class="product-tagline">Structured crown. Flat brim. Born to stand out, built to last.</p>
                    <p class="product-price">₹999</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="C:\Users\DELL\Downloads\A7400541.JPG"="Dad Hat" class="product-image">
                </div>
                <div class="product-info">
                    <p class="product-category">Unstructured</p>
                    <h3 class="product-name">The Icon</h3>
                    <p class="product-tagline">Effortlessly cool. Relaxed fit. The cap that goes everywhere, matches everything.</p>
                    <p class="product-price">₹799</p>
                    <button class="product-btn">Enquire Now</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Manifesto Section -->
    <section class="manifesto" id="story">
        <div class="manifesto-content">
            <h2>We Don't Make Accessories.<br>We Make Statements.</h2>
            <p>Every piece we craft carries a promise—that quality is non-negotiable, that style is personal, and that excellence is expected.</p>
            <p>We believe in leather that gets better with time. In stitching that holds under pressure. In designs that don't chase trends because they set them.</p>
            <p>This isn't fast fashion. This is heritage in the making. This is what happens when craftsmanship meets conviction.</p>
            <p class="manifesto-quote">"Your accessories don't complete your outfit.<br>They reveal your character."</p>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="testimonials">
        <div class="section-header">
            <p class="section-label">Words Worth Sharing</p>
            <h2 class="section-title">From Those Who Lead</h2>
        </div>
        <div class="testimonial-grid">
            <div class="testimonial">
                <div class="quote-mark">"</div>
                <p class="testimonial-text">The Executive belt transformed how I carry myself. It's not just about holding up pants—it's about holding up standards. This is the kind of quality that makes you walk taller.</p>
                <p class="testimonial-author">Arjun Mehta</p>
                <p class="testimonial-title">Entrepreneur, Mumbai</p>
            </div>
            <div class="testimonial">
                <div class="quote-mark">"</div>
                <p class="testimonial-text">I've bought expensive wallets before. But The Minimalist? It's different. It's the perfect balance of form and function. Finally, a wallet that doesn't compromise on either.</p>
                <p class="testimonial-author">Priya Sharma</p>
                <p class="testimonial-title">Creative Director, Bangalore</p>
            </div>
            <div class="testimonial">
                <div class="quote-mark">"</div>
                <p class="testimonial-text">The Aero cap is engineering meets style. It's so light, you forget you're wearing it, but everyone else notices. That's the kind of design intelligence I respect.</p>
                <p class="testimonial-author">Rohan Kapoor</p>
                <p class="testimonial-title">Tech Founder, Delhi</p>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <div class="newsletter-content">
            <h2>The Inner Circle</h2>
            <p>Exclusive drops. Early access. The first to know when excellence arrives.</p>
            <form class="newsletter-form">
                <input type="email" class="newsletter-input" placeholder="Your email address" required>
                <button type="submit" class="newsletter-btn">Join Now</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-brand">
                <h3>AVIGHNA</h3>
                <p>Crafting accessories for those who refuse to settle. Based in India, respected worldwide.</p>
            </div>
            <div class="footer-section">
                <h4>Shop</h4>
                <ul class="footer-links">
                    <li><a href="#belts">Belts</a></li>
                    <li><a href="#wallets">Wallets</a></li>
                    <li><a href="#caps">Caps</a></li>
                    <li><a href="#">New Arrivals</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h4>Support</h4>
                <ul class="footer-links">
                    <li><a href="#">Shipping & Returns</a></li>
                    <li><a href="#">Size Guide</a></li>
                    <li><a href="#">Care Instructions</a></li>
                    <li><a href="#">Contact Us</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h4>Company</h4>
                <ul class="footer-links">
                    <li><a href="#story">Our Story</a></li>
                    <li><a href="#">Craftsmanship</a></li>
                    <li><a href="#">Sustainability</a></li>
                    <li><a href="#">Careers</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 Avighna. All rights reserved. Crafted for those who lead.</p>
        </div>
    </footer>

    <!-- Enquiry Modal -->
    <div class="modal" id="enquiryModal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal()">×</button>
            
            <div class="enquiry-form-section">
                <h3>Enquire Now</h3>
                <p class="modal-product" id="selectedProduct"></p>
                
                <form id="enquiryForm">
                    <input type="hidden" id="productName" name="product">
                    
                    <div class="form-group">
                        <label for="name">Your Name *</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="mobile">Mobile Number *</label>
                        <input type="tel" id="mobile" name="mobile" pattern="[0-9]{10}" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="address">Address *</label>
                        <textarea id="address" name="address" required></textarea>
                    </div>
                    
                    <button type="submit" class="submit-btn">Submit Enquiry</button>
                </form>
            </div>
            
            <div class="success-message" id="successMessage">
                <div class="success-icon">✓</div>
                <h3>Thank You for Your Enquiry!</h3>
                <p>Our team will contact you shortly to assist with your purchase.</p>
            </div>
        </div>
    </div>

    <script>
        // Modal functionality
        const modal = document.getElementById('enquiryModal');
        const enquiryFormSection = document.querySelector('.enquiry-form-section');
        const successMessage = document.getElementById('successMessage');
        const enquiryForm = document.getElementById('enquiryForm');
        
        function openModal(productName) {
            modal.classList.add('active');
            document.getElementById('selectedProduct').textContent = productName;
            document.getElementById('productName').value = productName;
            document.body.style.overflow = 'hidden';
        }
        
        function closeModal() {
            modal.classList.remove('active');
            enquiryFormSection.style.display = 'block';
            successMessage.classList.remove('active');
            enquiryForm.reset();
            document.body.style.overflow = 'auto';
        }
        
        // Close modal when clicking outside
        modal.addEventListener('click', function(e) {
            if (e.target === modal) {
                closeModal();
            }
        });
        
        // Enquire Now buttons
        document.querySelectorAll('.product-btn').forEach(button => {
            button.addEventListener('click', function() {
                const card = this.closest('.product-card');
                const productName = card.querySelector('.product-name').textContent;
                openModal(productName);
            });
        });
        
        // Form submission
        enquiryForm.addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const formData = new FormData(this);
            const data = {
                product: formData.get('product'),
                name: formData.get('name'),
                mobile: formData.get('mobile'),
                address: formData.get('address')
            };
            
            // Prepare email content
            const emailBody = `
New Enquiry from Avighna Belts Website

Product: ${data.product}
Name: ${data.name}
Mobile: ${data.mobile}
Address: ${data.address}

---
This enquiry was submitted from avighna-belts.com
            `;
            
            // Send email using mailto (opens email client)
            const subject = encodeURIComponent(`New Enquiry: ${data.product}`);
            const body = encodeURIComponent(emailBody);
            const mailtoLink = `mailto:bhaveshsahu5331@gmail.com?subject=${subject}&body=${body}`;
            
            // For better user experience, we'll use a hidden form submission service
            // Using Web3Forms (free service) for actual email sending
            try {
                const response = await fetch('https://api.web3forms.com/submit', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                        'Accept': 'application/json'
                    },
                    body: JSON.stringify({
                        access_key: 'YOUR_ACCESS_KEY_HERE', // You'll need to get this from web3forms.com
                        subject: `New Enquiry: ${data.product}`,
                        from_name: 'Avighna Belts Website',
                        to_email: 'bhaveshsahu5331@gmail.com',
                        message: `
Product: ${data.product}
Name: ${data.name}
Mobile: ${data.mobile}
Address: ${data.address}
                        `
                    })
                });
                
                // Show success message
                enquiryFormSection.style.display = 'none';
                successMessage.classList.add('active');
                
                // Close modal after 3 seconds
                setTimeout(() => {
                    closeModal();
                }, 3000);
                
            } catch (error) {
                // Fallback to mailto if Web3Forms fails
                window.location.href = mailtoLink;
                
                // Still show success message
                enquiryFormSection.style.display = 'none';
                successMessage.classList.add('active');
                
                setTimeout(() => {
                    closeModal();
                }, 3000);
            }
        });

        // Smooth scrolling for navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 80,
                        behavior: 'smooth'
                });
                }
            });
        });

        // Cart button (keeping for navigation purposes)
        const cartBtn = document.querySelector('.cart-btn');
        cartBtn.addEventListener('click', () => {
            alert('Cart functionality coming soon! For now, please use "Enquire Now" on products.');
        });

        // Newsletter form
        document.querySelector('.newsletter-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = this.querySelector('input').value;
            alert('Welcome to the inner circle. Check your email for exclusive access.');
            this.reset();
        });

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.product-card, .testimonial').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
