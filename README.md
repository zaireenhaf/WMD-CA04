# WMD-CA04
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elegance Jewelry | Premium Collections</title>
    
    <!-- Bootstrap 5 CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;700&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <!-- Animate.css -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    
    <style>
        :root {
            --primary-color: #C19A6B;
            --secondary-color: #F8F5F0;
            --accent-color: #D4AF37;
            --dark-color: #1A1A1A;
            --light-color: #FFFFFF;
            --text-color: #333333;
            --gray-color: #888888;
            --transition: all 0.4s ease;
        }

        .dark-theme {
            --primary-color: #D4AF37;
            --secondary-color: #2A2A2A;
            --accent-color: #C19A6B;
            --dark-color: #121212;
            --light-color: #2A2A2A;
            --text-color: #F0F0F0;
            --gray-color: #AAAAAA;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: background-color 0.5s ease, color 0.3s ease;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            color: var(--text-color);
            background-color: var(--secondary-color);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4, h5 {
            font-family: 'Cormorant Garamond', serif;
            font-weight: 700;
            color: var(--primary-color);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: var(--secondary-color);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--primary-color);
            border-radius: 5px;
        }

        .dark-theme ::-webkit-scrollbar-track {
            background: var(--dark-color);
        }

        /* Navigation */
        .navbar {
            background-color: rgba(255, 255, 255, 0.95);
            padding: 20px 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .dark-theme .navbar {
            background-color: rgba(26, 26, 26, 0.95);
        }

        .navbar-brand {
            font-family: 'Cormorant Garamond', serif;
            font-weight: 700;
            font-size: 2rem;
            color: var(--primary-color) !important;
        }

        .nav-link {
            color: var(--text-color) !important;
            font-weight: 500;
            margin: 0 15px;
            position: relative;
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary-color);
            transition: width 0.3s ease;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        .theme-toggle {
            background-color: transparent;
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
            border-radius: 50%;
            width: 45px;
            height: 45px;
            cursor: pointer;
            transition: var(--transition);
        }

        .theme-toggle:hover {
            background-color: var(--primary-color);
            color: var(--light-color);
            transform: rotate(30deg);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: white;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            color: white;
            font-size: 4.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 30px;
        }

        .floating-jewelry {
            position: absolute;
            width: 150px;
            height: 150px;
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
            opacity: 0.7;
            animation: float 8s ease-in-out infinite;
            filter: drop-shadow(0 10px 20px rgba(0, 0, 0, 0.3));
        }

        .floating-jewelry:nth-child(1) {
            background-image: url('https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80');
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .floating-jewelry:nth-child(2) {
            background-image: url('https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80');
            top: 60%;
            right: 15%;
            animation-delay: 2s;
            width: 120px;
            height: 120px;
        }

        .floating-jewelry:nth-child(3) {
            background-image: url('https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80');
            bottom: 20%;
            left: 20%;
            animation-delay: 4s;
            width: 100px;
            height: 100px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(5deg); }
        }

        /* Section Styling */
        section {
            padding: 100px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background-color: var(--primary-color);
        }

        /* About Section */
        .about-video {
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        .video-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, transparent 70%, rgba(0,0,0,0.8));
            display: flex;
            align-items: flex-end;
            padding: 30px;
            color: white;
        }

        /* Collections Section */
        .collection-card {
            background-color: var(--light-color);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.08);
            transition: var(--transition);
            margin-bottom: 30px;
            height: 100%;
            position: relative;
        }

        .collection-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
        }

        .collection-img {
            width: 100%;
            height: 300px;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .collection-card:hover .collection-img {
            transform: scale(1.05);
        }

        .collection-info {
            padding: 25px;
        }

        .collection-badge {
            display: inline-block;
            background-color: var(--primary-color);
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        /* Product Grid */
        .product-grid {
            background-color: var(--secondary-color);
        }

        .product-card {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            margin-bottom: 30px;
            background-color: var(--light-color);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .product-img {
            width: 100%;
            height: 350px;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .product-card:hover .product-img {
            transform: scale(1.05);
        }

        .product-info {
            padding: 20px;
        }

        .product-price {
            color: var(--primary-color);
            font-weight: 700;
            font-size: 1.3rem;
            margin-top: 10px;
        }

        .product-rating {
            color: #FFD700;
            margin: 10px 0;
        }

        /* Testimonials */
        .testimonial-section {
            background-color: var(--light-color);
        }

        .testimonial-card {
            background-color: var(--secondary-color);
            border-radius: 15px;
            padding: 30px;
            margin: 20px 0;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .testimonial-card:hover {
            transform: translateY(-10px);
        }

        .testimonial-img {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 20px;
            border: 3px solid var(--primary-color);
        }

        /* Contact Form */
        .contact-form {
            background-color: var(--light-color);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.08);
        }

        .form-control {
            background-color: var(--secondary-color);
            border: 1px solid var(--primary-color);
            color: var(--text-color);
            padding: 12px 15px;
            margin-bottom: 20px;
            border-radius: 8px;
        }

        .form-control:focus {
            border-color: var(--accent-color);
            box-shadow: 0 0 0 0.25rem rgba(193, 154, 107, 0.25);
        }

        /* 3D Jewelry Viewer */
        .jewelry-3d-viewer {
            height: 500px;
            background: linear-gradient(45deg, var(--secondary-color), var(--light-color));
            border-radius: 15px;
            overflow: hidden;
            position: relative;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
        }

        .jewelry-3d-element {
            position: absolute;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, var(--primary-color) 0%, transparent 70%);
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation: spin 20s linear infinite;
            box-shadow: 0 0 100px rgba(193, 154, 107, 0.5);
        }

        @keyframes spin {
            0% { transform: translate(-50%, -50%) rotate(0deg); }
            100% { transform: translate(-50%, -50%) rotate(360deg); }
        }

        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: #c9c9c9;
            padding: 80px 0 20px;
        }

        .footer-logo {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 20px;
        }

        .social-icons a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--primary-color);
            border-radius: 50%;
            margin-right: 10px;
            transition: var(--transition);
        }

        .social-icons a:hover {
            background-color: var(--primary-color);
            color: var(--dark-color);
            transform: translateY(-5px);
        }

        /* Loading Animation */
        .loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--secondary-color);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s ease, visibility 0.5s ease;
        }

        .dark-theme .loader {
            background-color: var(--dark-color);
        }

        .jewelry-loader {
            width: 100px;
            height: 100px;
            position: relative;
        }

        .diamond {
            width: 50px;
            height: 50px;
            background-color: var(--primary-color);
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) rotate(45deg);
            animation: pulse 2s ease-in-out infinite;
            box-shadow: 0 0 30px rgba(193, 154, 107, 0.7);
        }

        @keyframes pulse {
            0%, 100% { transform: translate(-50%, -50%) rotate(45deg) scale(1); }
            50% { transform: translate(-50%, -50%) rotate(45deg) scale(1.2); }
        }

        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background-color: var(--primary-color);
            color: var(--light-color);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 1000;
        }

        .back-to-top.show {
            opacity: 1;
            visibility: visible;
        }

        .back-to-top:hover {
            background-color: var(--accent-color);
            transform: translateY(-5px);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            section {
                padding: 60px 0;
            }
            
            .floating-jewelry {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loader" id="loader">
        <div class="jewelry-loader">
            <div class="diamond"></div>
        </div>
    </div>

    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-light fixed-top">
        <div class="container">
            <a class="navbar-brand" href="#home">Elegance Jewelry</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="#home">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#about">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#collections">Collections</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#products">Products</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#testimonials">Testimonials</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#contact">Contact</a>
                    </li>
                </ul>
                <button class="btn theme-toggle ms-3" id="themeToggle">
                    <i class="fas fa-moon"></i>
                </button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="floating-jewelry"></div>
        <div class="floating-jewelry"></div>
        <div class="floating-jewelry"></div>
        <div class="container">
            <div class="row justify-content-center text-center">
                <div class="col-lg-8">
                    <h1 class="animate__animated animate__fadeInDown">Timeless Elegance in Every Piece</h1>
                    <p class="animate__animated animate__fadeInUp animate__delay-1s">Discover our exclusive collection of handcrafted jewelry, where luxury meets artistry in every meticulously designed piece.</p>
                    <a href="#collections" class="btn btn-outline-light btn-lg animate__animated animate__fadeInUp animate__delay-2s">Explore Collections</a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-5">
        <div class="container py-5">
            <h2 class="section-title animate__animated animate__fadeInUp">Our Story</h2>
            <div class="row align-items-center mt-5">
                <div class="col-lg-6 mb-5 mb-lg-0">
                    <div class="about-video animate__animated animate__fadeInLeft">
                        <video width="100%" autoplay muted loop>
                            <source src="https://assets.mixkit.co/videos/preview/mixkit-close-up-of-a-jewelry-maker-at-work-41645-large.mp4" type="video/mp4">
                            Your browser does not support the video tag.
                        </video>
                        <div class="video-overlay">
                            <div>
                                <h4 class="text-white">Craftsmanship Excellence</h4>
                                <p>Our artisans at work</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-6">
                    <div class="ps-lg-5 animate__animated animate__fadeInRight">
                        <h3 class="mb-4">A Legacy of Craftsmanship Since 1890</h3>
                        <p class="mb-4">At Elegance Jewelry, we believe that fine jewelry is more than an accessory—it's an expression of personal style, a celebration of life's milestones, and a legacy to be treasured for generations.</p>
                        <p class="mb-4">Each piece is meticulously crafted by our master artisans, combining traditional techniques with contemporary design to create timeless works of art.</p>
                        <div class="row mt-4">
                            <div class="col-md-6">
                                <ul class="list-unstyled">
                                    <li class="mb-3"><i class="fas fa-gem text-primary me-2"></i> Ethically sourced diamonds</li>
                                    <li class="mb-3"><i class="fas fa-hands text-primary me-2"></i> Handcrafted by artisans</li>
                                    <li class="mb-3"><i class="fas fa-award text-primary me-2"></i> Lifetime warranty</li>
                                </ul>
                            </div>
                            <div class="col-md-6">
                                <ul class="list-unstyled">
                                    <li class="mb-3"><i class="fas fa-recycle text-primary me-2"></i> Recycled precious metals</li>
                                    <li class="mb-3"><i class="fas fa-certificate text-primary me-2"></i> GIA certified gems</li>
                                    <li class="mb-3"><i class="fas fa-shipping-fast text-primary me-2"></i> Worldwide delivery</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Collections Section -->
    <section id="collections" class="py-5" style="background-color: var(--light-color);">
        <div class="container py-5">
            <h2 class="section-title animate__animated animate__fadeInUp">Our Collections</h2>
            <p class="text-center mb-5 animate__animated animate__fadeInUp animate__delay-1s">Explore our exclusive jewelry collections, each telling a unique story</p>
            
            <div class="row">
                <div class="col-lg-4 col-md-6 mb-4 animate__animated animate__fadeInUp">
                    <div class="collection-card">
                        <img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="collection-img" alt="Diamond Collection">
                        <div class="collection-info">
                            <span class="collection-badge">Diamond</span>
                            <h4>Eternal Brilliance</h4>
                            <p>A collection featuring the finest diamonds set in platinum and 18k gold, designed for timeless elegance.</p>
                            <a href="#" class="btn btn-outline-primary mt-3">View Collection</a>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-4 col-md-6 mb-4 animate__animated animate__fadeInUp animate__delay-1s">
                    <div class="collection-card">
                        <img src="https://images.unsplash.com/photo-1515562141207-7a88fb7ce338?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="collection-img" alt="Gold Collection">
                        <div class="collection-info">
                            <span class="collection-badge">Gold</span>
                            <h4>Golden Heritage</h4>
                            <p>Classic and contemporary designs in 18k and 22k gold, celebrating the warmth and luxury of this precious metal.</p>
                            <a href="#" class="btn btn-outline-primary mt-3">View Collection</a>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-4 col-md-6 mb-4 animate__animated animate__fadeInUp animate__delay-2s">
                    <div class="collection-card">
                        <img src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="collection-img" alt="Pearl Collection">
                        <div class="collection-info">
                            <span class="collection-badge">Pearl</span>
                            <h4>Ocean's Treasure</h4>
                            <p>Elegant pearl jewelry featuring South Sea, Tahitian, and Akoya pearls, perfect for sophisticated occasions.</p>
                            <a href="#" class="btn btn-outline-primary mt-3">View Collection</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 3D Jewelry Viewer -->
    <section class="py-5">
        <div class="container py-5">
            <h2 class="section-title animate__animated animate__fadeInUp">Interactive 3D Jewelry Viewer</h2>
            <p class="text-center mb-5 animate__animated animate__fadeInUp animate__delay-1s">Explore our jewelry in stunning 3D detail</p>
            
            <div class="jewelry-3d-viewer animate__animated animate__zoomIn">
                <div class="jewelry-3d-element"></div>
                <div class="position-absolute top-0 start-0 w-100 h-100 d-flex align-items-center justify-content-center">
                    <div class="text-center text-white p-4" style="background-color: rgba(0,0,0,0.7); border-radius: 15px;">
                        <h3>3D Jewelry Experience</h3>
                        <p>Rotate and zoom to explore every detail of our exquisite pieces</p>
                        <button class="btn btn-primary mt-3" id="rotate3D">Start 3D Rotation</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="product-grid py-5">
        <div class="container py-5">
            <h2 class="section-title animate__animated animate__fadeInUp">Featured Products</h2>
            <p class="text-center mb-5 animate__animated animate__fadeInUp animate__delay-1s">Discover our most exquisite jewelry pieces</p>
            
            <div class="row">
                <div class="col-lg-3 col-md-6 mb-4 animate__animated animate__fadeInUp">
                    <div class="product-card">
                        <img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="product-img" alt="Diamond Necklace">
                        <div class="product-info">
                            <h5>Solitaire Diamond Necklace</h5>
                            <div class="product-rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star-half-alt"></i>
                                <span class="ms-2">(4.5)</span>
                            </div>
                            <p class="text-muted">1.5 carat diamond in platinum setting</p>
                            <div class="product-price">$8,500</div>
                            <button class="btn btn-primary w-100 mt-3">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6 mb-4 animate__animated animate__fadeInUp animate__delay-1s">
                    <div class="product-card">
                        <img src="https://images.unsplash.com/photo-1515562141207-7a88fb7ce338?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="product-img" alt="Gold Bracelet">
                        <div class="product-info">
                            <h5>18k Gold Bangle Bracelet</h5>
                            <div class="product-rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="far fa-star"></i>
                                <span class="ms-2">(4.0)</span>
                            </div>
                            <p class="text-muted">Solid 18k gold with intricate detailing</p>
                            <div class="product-price">$2,800</div>
                            <button class="btn btn-primary w-100 mt-3">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6 mb-4 animate__animated animate__fadeInUp animate__delay-2s">
                    <div class="product-card">
                        <img src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="product-img" alt="Pearl Earrings">
                        <div class="product-info">
                            <h5>South Sea Pearl Earrings</h5>
                            <div class="product-rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <span class="ms-2">(5.0)</span>
                            </div>
                            <p class="text-muted">12mm South Sea pearls with diamond accents</p>
                            <div class="product-price">$5,200</div>
                            <button class="btn btn-primary w-100 mt-3">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-3 col-md-6 mb-4 animate__animated animate__fadeInUp animate__delay-3s">
                    <div class="product-card">
                        <img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="product-img" alt="Emerald Ring">
                        <div class="product-info">
                            <h5>Emerald & Diamond Ring</h5>
                            <div class="product-rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star-half-alt"></i>
                                <span class="ms-2">(4.5)</span>
                            </div>
                            <p class="text-muted">2 carat emerald with diamond halo setting</p>
                            <div class="product-price">$7,500</div>
                            <button class="btn btn-primary w-100 mt-3">Add to Cart</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="testimonial-section py-5">
        <div class="container py-5">
            <h2 class="section-title animate__animated animate__fadeInUp">Customer Testimonials</h2>
            <p class="text-center mb-5 animate__animated animate__fadeInUp animate__delay-1s">What our customers say about us</p>
            
            <div class="row">
                <div class="col-lg-4 mb-4 animate__animated animate__fadeInLeft">
                    <div class="testimonial-card">
                        <img src="https://miniprojectorreviews.com/_next/image?url=%2Fimages%2Fauthors%2Fsarah-johnson.png&w=3840&q=75" class="testimonial-img" alt="Sarah Johnson">
                        <h5>Sarah Johnson</h5>
                        <p class="text-muted">Purchased: Diamond Engagement Ring</p>
                        <p>"The craftsmanship is exceptional. My engagement ring is more beautiful than I ever imagined. The attention to detail is remarkable!"</p>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-4 mb-4 animate__animated animate__fadeInUp">
                    <div class="testimonial-card">
                        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80" class="testimonial-img" alt="Michael Chen">
                        <h5>Michael Chen</h5>
                        <p class="text-muted">Purchased: Pearl Necklace</p>
                        <p>"I bought the pearl necklace for my wife's anniversary. The quality is outstanding and the customer service was impeccable."</p>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-4 mb-4 animate__animated animate__fadeInRight">
                    <div class="testimonial-card">
                        <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80" class="testimonial-img" alt="Emily Rodriguez">
                        <h5>Emily Rodriguez</h5>
                        <p class="text-muted">Purchased: Gold Bangle Set</p>
                        <p>"The gold bangles are stunning and so comfortable to wear. I receive compliments every time I wear them. Worth every penny!"</p>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-5">
        <div class="container py-5">
            <h2 class="section-title animate__animated animate__fadeInUp">Contact Us</h2>
            <p class="text-center mb-5 animate__animated animate__fadeInUp animate__delay-1s">Get in touch for custom designs or consultations</p>
            
            <div class="row">
                <div class="col-lg-8 mx-auto">
                    <div class="contact-form animate__animated animate__zoomIn">
                        <form id="contactForm">
                            <div class="row">
                                <div class="col-md-6">
                                    <div class="mb-3">
                                        <input type="text" class="form-control" id="name" placeholder="Your Name" required>
                                    </div>
                                </div>
                                <div class="col-md-6">
                                    <div class="mb-3">
                                        <input type="email" class="form-control" id="email" placeholder="Your Email" required>
                                    </div>
                                </div>
                            </div>
                            <div class="mb-3">
                                <input type="text" class="form-control" id="subject" placeholder="Subject" required>
                            </div>
                            <div class="mb-3">
                                <textarea class="form-control" id="message" rows="5" placeholder="Your Message" required></textarea>
                            </div>
                            <button type="submit" class="btn btn-primary btn-lg w-100">Send Message</button>
                        </form>
                    </div>
                    
                    <div class="row mt-5">
                        <div class="col-md-4 text-center mb-4 animate__animated animate__fadeInUp">
                            <div class="p-4 rounded" style="background-color: var(--light-color);">
                                <i class="fas fa-map-marker-alt fa-2x mb-3" style="color: var(--primary-color);"></i>
                                <h5>Visit Our Boutique</h5>
                                <p>123 Diamond Avenue<br>New York, NY 10001</p>
                            </div>
                        </div>
                        <div class="col-md-4 text-center mb-4 animate__animated animate__fadeInUp animate__delay-1s">
                            <div class="p-4 rounded" style="background-color: var(--light-color);">
                                <i class="fas fa-phone fa-2x mb-3" style="color: var(--primary-color);"></i>
                                <h5>Call Us</h5>
                                <p>+1 (212) 555-1234<br>Mon-Sat: 10am-8pm</p>
                            </div>
                        </div>
                        <div class="col-md-4 text-center mb-4 animate__animated animate__fadeInUp animate__delay-2s">
                            <div class="p-4 rounded" style="background-color: var(--light-color);">
                                <i class="fas fa-envelope fa-2x mb-3" style="color: var(--primary-color);"></i>
                                <h5>Email Us</h5>
                                <p>info@elegancejewelry.com<br>custom@elegancejewelry.com</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="row">
                <div class="col-lg-4 mb-4">
                    <div class="footer-logo">Elegance Jewelry</div>
                    <p>Creating exquisite jewelry since 1890. Each piece tells a unique story through meticulous craftsmanship.</p>
                    <div class="social-icons mt-4">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-pinterest-p"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
                <div class="col-lg-2 col-md-6 mb-4">
                    <h5 class="mb-4 text-white">Collections</h5>
                    <ul class="list-unstyled">
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Diamond</a></li>
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Gold</a></li>
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Pearl</a></li>
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Platinum</a></li>
                    </ul>
                </div>
                <div class="col-lg-3 col-md-6 mb-4">
                    <h5 class="mb-4 text-white">Services</h5>
                    <ul class="list-unstyled">
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Custom Design</a></li>
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Jewelry Repair</a></li>
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Appraisal</a></li>
                        <li class="mb-2"><a href="#" class="text-light text-decoration-none">Engagement Rings</a></li>
                    </ul>
                </div>
                <div class="col-lg-3 mb-4">
                    <h5 class="mb-4 text-white">Newsletter</h5>
                    <p>Subscribe for exclusive offers and new collection previews.</p>
                    <div class="input-group mb-3">
                        <input type="email" class="form-control" placeholder="Your Email">
                        <button class="btn btn-outline-light" type="button">Subscribe</button>
                    </div>
                </div>
            </div>
            <hr class="mt-4 mb-4" style="border-color: #555;">
            <div class="text-center pt-3">
                <p>&copy; 2023 Elegance Jewelry. All rights reserved. | Final Project - Web & Multimedia Application</p>
            </div>
        </div>
    </footer>

    <!-- Back to Top Button -->
    <div class="back-to-top" id="backToTop">
        <i class="fas fa-chevron-up"></i>
    </div>

    <!-- Bootstrap JS Bundle -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
    
    <script>
        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            // Loading screen
            setTimeout(() => {
                document.getElementById('loader').style.opacity = '0';
                document.getElementById('loader').style.visibility = 'hidden';
            }, 1500);

            // Theme Toggle
            const themeToggle = document.getElementById('themeToggle');
            themeToggle.addEventListener('click', function() {
                document.body.classList.toggle('dark-theme');
                const icon = this.querySelector('i');
                if (document.body.classList.contains('dark-theme')) {
                    icon.classList.remove('fa-moon');
                    icon.classList.add('fa-sun');
                    localStorage.setItem('theme', 'dark');
                } else {
                    icon.classList.remove('fa-sun');
                    icon.classList.add('fa-moon');
                    localStorage.setItem('theme', 'light');
                }
            });

            // Check for saved theme
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme === 'dark') {
                document.body.classList.add('dark-theme');
                themeToggle.querySelector('i').classList.remove('fa-moon');
                themeToggle.querySelector('i').classList.add('fa-sun');
            }

            // Smooth scrolling for navigation
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                });
            });

            // Form submission
            document.getElementById('contactForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                // Simple form validation
                const name = document.getElementById('name').value;
                const email = document.getElementById('email').value;
                const message = document.getElementById('message').value;
                
                if(name && email && message) {
                    // Show success message
                    alert('Thank you for your message, ' + name + '! We will get back to you soon.');
                    this.reset();
                } else {
                    alert('Please fill in all required fields.');
                }
            });

            // Back to top button
            const backToTopButton = document.getElementById('backToTop');
            
            window.addEventListener('scroll', function() {
                if (window.pageYOffset > 300) {
                    backToTopButton.classList.add('show');
                } else {
                    backToTopButton.classList.remove('show');
                }
            });
            
            backToTopButton.addEventListener('click', function() {
                window.scrollTo({
                    top: 0,
                    behavior: 'smooth'
                });
            });

            // 3D Rotation Animation
            const rotate3DButton = document.getElementById('rotate3D');
            const jewelry3DElement = document.querySelector('.jewelry-3d-element');
            let isRotating = false;
            let rotationSpeed = 1;
            
            rotate3DButton.addEventListener('click', function() {
                if (!isRotating) {
                    isRotating = true;
                    this.textContent = 'Stop Rotation';
                    jewelry3DElement.style.animation = `spin ${20/rotationSpeed}s linear infinite`;
                } else {
                    isRotating = false;
                    this.textContent = 'Start 3D Rotation';
                    jewelry3DElement.style.animation = 'none';
                }
            });

            // Product card animations on hover
            const productCards = document.querySelectorAll('.product-card');
            
            productCards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-15px)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(-10px)';
                });
            });

            // Collection card animations
            const collectionCards = document.querySelectorAll('.collection-card');
            
            collectionCards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-15px)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });

            // Testimonial card animations
            const testimonialCards = document.querySelectorAll('.testimonial-card');
            
            testimonialCards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-10px)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });

            // Add to cart functionality
            const addToCartButtons = document.querySelectorAll('.product-card .btn-primary');
            
            addToCartButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const productName = this.closest('.product-info').querySelector('h5').textContent;
                    const productPrice = this.closest('.product-info').querySelector('.product-price').textContent;
                    
                    // Show confirmation
                    const confirmation = confirm(`Add "${productName}" (${productPrice}) to cart?`);
                    
                    if (confirmation) {
                        // Animate button
                        this.innerHTML = '<i class="fas fa-check me-2"></i> Added to Cart';
                        this.classList.remove('btn-primary');
                        this.classList.add('btn-success');
                        
                        // Reset button after 2 seconds
                        setTimeout(() => {
                            this.innerHTML = 'Add to Cart';
                            this.classList.remove('btn-success');
                            this.classList.add('btn-primary');
                        }, 2000);
                    }
                });
            });

            // Newsletter subscription
            const newsletterBtn = document.querySelector('.btn-outline-light');
            const newsletterInput = document.querySelector('.input-group input[type="email"]');
            
            newsletterBtn.addEventListener('click', function() {
                if(newsletterInput.value) {
                    alert('Thank you for subscribing to our newsletter!');
                    newsletterInput.value = '';
                } else {
                    alert('Please enter your email address.');
                }
            });

            // Scroll animations
            const animateOnScroll = () => {
                const elements = document.querySelectorAll('.animate__animated');
                
                elements.forEach(element => {
                    const elementPosition = element.getBoundingClientRect().top;
                    const screenPosition = window.innerHeight / 1.3;
                    
                    if (elementPosition < screenPosition) {
                        const animationClass = element.classList[1];
                        element.classList.add(animationClass);
                    }
                });
            };
            
            window.addEventListener('scroll', animateOnScroll);
            // Initial trigger
            animateOnScroll();
        });
    </script>
</body>
</html>
