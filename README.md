<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Glamour Cosmetics - Premium Beauty Products</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary-color: #ff85a2;
            --secondary-color: #ffd6e0;
            --accent-color: #c81d5f;
            --text-color: #333;
            --light-text: #777;
            --bg-color: #fff9fb;
            --card-bg: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background-color: var(--card-bg);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--accent-color);
            text-decoration: none;
            display: flex;
            align-items: center;
        }

        .logo i {
            margin-right: 10px;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 25px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        .header-icons {
            display: flex;
            align-items: center;
        }

        .header-icons a {
            color: var(--text-color);
            margin-left: 20px;
            font-size: 18px;
            transition: color 0.3s;
        }

        .header-icons a:hover {
            color: var(--accent-color);
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            color: var(--text-color);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--secondary-color), var(--primary-color));
            padding: 80px 0;
            text-align: center;
            color: white;
        }

        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 18px;
            max-width: 700px;
            margin: 0 auto 30px;
        }

        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            background-color: #a6174b;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        /* Admin Controls */
        .admin-controls {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
        }

        .admin-btn {
            background-color: var(--accent-color);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        .admin-panel {
            position: fixed;
            bottom: 80px;
            right: 20px;
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.15);
            width: 300px;
            display: none;
        }

        .admin-panel h3 {
            margin-bottom: 15px;
            color: var(--accent-color);
        }

        .admin-panel input, .admin-panel select {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        /* Sections */
        .section {
            padding: 60px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 40px;
        }

        .section-title h2 {
            font-size: 32px;
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .section-title p {
            color: var(--light-text);
            max-width: 700px;
            margin: 0 auto;
        }

        /* Product Grid */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }

        .product-card {
            background-color: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .product-image {
            height: 250px;
            overflow: hidden;
            position: relative;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.05);
        }

        .product-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background-color: var(--accent-color);
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 12px;
            font-weight: 600;
        }

        .product-info {
            padding: 20px;
        }

        .product-category {
            color: var(--light-text);
            font-size: 14px;
            margin-bottom: 5px;
        }

        .product-name {
            font-size: 18px;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .product-price {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .current-price {
            font-size: 20px;
            font-weight: 700;
            color: var(--accent-color);
        }

        .original-price {
            font-size: 16px;
            color: var(--light-text);
            text-decoration: line-through;
            margin-left: 10px;
        }

        .product-rating {
            color: #ffc107;
            margin-bottom: 15px;
        }

        .product-actions {
            display: flex;
            justify-content: space-between;
        }

        .add-to-cart {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .add-to-cart:hover {
            background-color: var(--accent-color);
        }

        .wishlist-btn {
            background: none;
            border: none;
            color: var(--light-text);
            font-size: 18px;
            cursor: pointer;
            transition: color 0.3s;
        }

        .wishlist-btn:hover {
            color: var(--accent-color);
        }

        /* Testimonials */
        .testimonials {
            background-color: var(--secondary-color);
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
            color: var(--text-color);
        }

        .testimonial-author {
            display: flex;
            align-items: center;
        }

        .author-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 15px;
        }

        .author-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .author-info h4 {
            font-size: 16px;
            margin-bottom: 5px;
        }

        .author-info p {
            font-size: 14px;
            color: var(--light-text);
        }

        /* Footer */
        footer {
            background-color: #2a2a2a;
            color: white;
            padding: 60px 0 20px;
        }

        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h3 {
            font-size: 18px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-col h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 50px;
            height: 2px;
            background-color: var(--primary-color);
        }

        .footer-col ul {
            list-style: none;
        }

        .footer-col ul li {
            margin-bottom: 10px;
        }

        .footer-col ul li a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-col ul li a:hover {
            color: var(--primary-color);
        }

        .footer-col p {
            color: #ddd;
            margin-bottom: 15px;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-links a {
            color: white;
            background-color: #444;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background-color: var(--primary-color);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #444;
            color: #aaa;
            font-size: 14px;
        }

        /* Side App Button */
        .side-app {
            position: fixed;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            background-color: var(--accent-color);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            z-index: 100;
        }

        /* Shopping Cart */
        .cart-overlay {
            position: fixed;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            display: none;
            justify-content: flex-end;
        }

        .cart-container {
            width: 100%;
            max-width: 400px;
            height: 100%;
            background-color: white;
            padding: 20px;
            overflow-y: auto;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1px solid #eee;
        }

        .cart-header h3 {
            font-size: 20px;
        }

        .close-cart {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
        }

        .cart-items {
            margin-bottom: 30px;
        }

        .cart-item {
            display: flex;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid #eee;
        }

        .cart-item-img {
            width: 80px;
            height: 80px;
            margin-right: 15px;
        }

        .cart-item-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 5px;
        }

        .cart-item-info {
            flex: 1;
        }

        .cart-item-name {
            font-weight: 600;
            margin-bottom: 5px;
        }

        .cart-item-price {
            color: var(--accent-color);
            font-weight: 600;
            margin-bottom: 5px;
        }

        .cart-item-remove {
            color: var(--light-text);
            font-size: 12px;
            cursor: pointer;
        }

        .cart-item-remove:hover {
            color: var(--accent-color);
        }

        .cart-item-quantity {
            display: flex;
            align-items: center;
            margin-top: 10px;
        }

        .quantity-btn {
            width: 25px;
            height: 25px;
            border: 1px solid #ddd;
            background: none;
            cursor: pointer;
        }

        .quantity-input {
            width: 40px;
            height: 25px;
            text-align: center;
            border: 1px solid #ddd;
            border-left: none;
            border-right: none;
        }

        .cart-total {
            margin-bottom: 20px;
            text-align: right;
        }

        .cart-total h4 {
            font-size: 18px;
        }

        .cart-total span {
            color: var(--accent-color);
            font-weight: 700;
        }

        .checkout-btn {
            width: 100%;
            padding: 12px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .checkout-btn:hover {
            background-color: #a6174b;
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: var(--card-bg);
                flex-direction: column;
                align-items: center;
                padding-top: 30px;
                transition: left 0.3s;
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 15px 0;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 36px;
            }

            .section {
                padding: 40px 0;
            }

            .side-app {
                left: 10px;
                width: 40px;
                height: 40px;
                font-size: 16px;
            }
        }

        @media (max-width: 576px) {
            .hero h1 {
                font-size: 28px;
            }

            .hero p {
                font-size: 16px;
            }

            .btn {
                padding: 10px 20px;
            }

            .section-title h2 {
                font-size: 26px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-spa"></i> Glamour
            </a>
            
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
            
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#skincare">Skincare</a></li>
                <li><a href="#makeup">Makeup</a></li>
                <li><a href="#bestsellers">Bestsellers</a></li>
                <li><a href="#new-arrivals">New Arrivals</a></li>
                <li><a href="#testimonials">Reviews</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            
            <div class="header-icons">
                <a href="#" class="search-btn"><i class="fas fa-search"></i></a>
                <a href="#" class="user-btn"><i class="fas fa-user"></i></a>
                <a href="#" class="cart-btn"><i class="fas fa-shopping-cart"></i></a>
            </div>
        </div>
    </header>

    <!-- Side App Button -->
    <div class="side-app">
        <i class="fas fa-mobile-alt"></i>
    </div>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Discover Your Beauty</h1>
            <p>Premium quality cosmetics made with natural ingredients to enhance your natural beauty. Shop our collection of skincare and makeup products.</p>
            <a href="#new-arrivals" class="btn">Shop Now</a>
        </div>
    </section>

    <!-- Skincare Section -->
    <section class="section" id="skincare">
        <div class="container">
            <div class="section-title">
                <h2>Skincare Essentials</h2>
                <p>Nourish your skin with our carefully formulated skincare products designed for all skin types.</p>
            </div>
            
            <div class="product-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1571781926291-c477ebfd024b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Hydrating Face Moisturizer">
                        <span class="product-badge">Bestseller</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Moisturizer</p>
                        <h3 class="product-name">Hydrating Face Moisturizer</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,499</span>
                            <span class="original-price">Rs 2,000</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <span>(42)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1596755094514-f87e34085b2c?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Vitamin C Serum">
                    </div>
                    <div class="product-info">
                        <p class="product-category">Serum</p>
                        <h3 class="product-name">Vitamin C Brightening Serum</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 2,199</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                            <span>(28)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1556228578-8c89e6adf883?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Cleansing Oil">
                        <span class="product-badge">New</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Cleanser</p>
                        <h3 class="product-name">Gentle Cleansing Oil</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,799</span>
                            <span class="original-price">Rs 2,200</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <span>(35)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 4 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1570172619644-dfd03ed5d881?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Night Cream">
                    </div>
                    <div class="product-info">
                        <p class="product-category">Night Care</p>
                        <h3 class="product-name">Revitalizing Night Cream</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 2,499</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <span>(19)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Makeup Section -->
    <section class="section" id="makeup">
        <div class="container">
            <div class="section-title">
                <h2>Makeup Collection</h2>
                <p>Enhance your natural beauty with our high-quality, long-lasting makeup products.</p>
            </div>
            
            <div class="product-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1596462502278-27bfdc403348?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Matte Lipstick">
                        <span class="product-badge">Bestseller</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Lipstick</p>
                        <h3 class="product-name">Velvet Matte Lipstick</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,199</span>
                            <span class="original-price">Rs 1,500</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <span>(56)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1522335789203-aabd1fc54bc9?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Foundation">
                    </div>
                    <div class="product-info">
                        <p class="product-category">Foundation</p>
                        <h3 class="product-name">Natural Finish Foundation</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 2,599</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                            <span>(34)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1625772452859-1c03d5bf1137?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Eyeshadow Palette">
                        <span class="product-badge">New</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Eyeshadow</p>
                        <h3 class="product-name">Nude Eyeshadow Palette</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 3,199</span>
                            <span class="original-price">Rs 3,800</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <span>(27)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 4 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1572490122747-3968b75cc699?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Mascara">
                    </div>
                    <div class="product-info">
                        <p class="product-category">Mascara</p>
                        <h3 class="product-name">Volume Boost Mascara</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,499</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                            <span>(41)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Bestsellers Section -->
    <section class="section" id="bestsellers">
        <div class="container">
            <div class="section-title">
                <h2>Our Bestsellers</h2>
                <p>Discover our most loved products by customers across Pakistan.</p>
            </div>
            
            <div class="product-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1596755094514-f87e34085b2c?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Vitamin C Serum">
                        <span class="product-badge">Bestseller</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Serum</p>
                        <h3 class="product-name">Vitamin C Brightening Serum</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 2,199</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                            <span>(28)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1596462502278-27bfdc403348?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Matte Lipstick">
                        <span class="product-badge">Bestseller</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Lipstick</p>
                        <h3 class="product-name">Velvet Matte Lipstick</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,199</span>
                            <span class="original-price">Rs 1,500</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <span>(56)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1570172619644-dfd03ed5d881?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Night Cream">
                        <span class="product-badge">Bestseller</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Night Care</p>
                        <h3 class="product-name">Revitalizing Night Cream</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 2,499</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <span>(19)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 4 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1572490122747-3968b75cc699?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Mascara">
                        <span class="product-badge">Bestseller</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Mascara</p>
                        <h3 class="product-name">Volume Boost Mascara</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,499</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                            <span>(41)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- New Arrivals Section -->
    <section class="section" id="new-arrivals">
        <div class="container">
            <div class="section-title">
                <h2>New Arrivals</h2>
                <p>Discover our latest products that just arrived in store.</p>
            </div>
            
            <div class="product-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1625772452859-1c03d5bf1137?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Eyeshadow Palette">
                        <span class="product-badge">New</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Eyeshadow</p>
                        <h3 class="product-name">Nude Eyeshadow Palette</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 3,199</span>
                            <span class="original-price">Rs 3,800</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <span>(27)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1556228578-8c89e6adf883?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Cleansing Oil">
                        <span class="product-badge">New</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Cleanser</p>
                        <h3 class="product-name">Gentle Cleansing Oil</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,799</span>
                            <span class="original-price">Rs 2,200</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <span>(35)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1574285013029-29296a71930e?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Blush">
                        <span class="product-badge">New</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Blush</p>
                        <h3 class="product-name">Cream Blush Stick</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 1,299</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                            <span>(12)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 4 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1595341595379-cf0f2a5d3405?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Face Mist">
                        <span class="product-badge">New</span>
                    </div>
                    <div class="product-info">
                        <p class="product-category">Face Mist</p>
                        <h3 class="product-name">Hydrating Rose Face Mist</h3>
                        <div class="product-price">
                            <span class="current-price">Rs 999</span>
                            <span class="original-price">Rs 1,200</span>
                        </div>
                        <div class="product-rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <span>(8)</span>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart">Add to Cart</button>
                            <button class="wishlist-btn"><i class="far fa-heart"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="section testimonials" id="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>Customer Reviews</h2>
                <p>What our Pakistani customers say about our products.</p>
            </div>
            
            <div class="testimonial-grid">
                <!-- Testimonial 1 -->
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "The Vitamin C Serum has completely transformed my skin! I've been using it for a month and my dark spots have faded significantly. Highly recommended to all Pakistani women looking for effective skincare."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="https://randomuser.me/api/portraits/women/42.jpg" alt="Aisha Khan">
                        </div>
                        <div class="author-info">
                            <h4>Aisha Khan</h4>
                            <p>Lahore, Pakistan</p>
                        </div>
                    </div>
                </div>
                
                <!-- Testimonial 2 -->
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "I'm in love with the Velvet Matte Lipstick! The shade range is perfect for Pakistani skin tones and it stays on all day without drying my lips. Worth every rupee!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="https://randomuser.me/api/portraits/women/65.jpg" alt="Fatima Ahmed">
                        </div>
                        <div class="author-info">
                            <h4>Fatima Ahmed</h4>
                            <p>Karachi, Pakistan</p>
                        </div>
                    </div>
                </div>
                
                <!-- Testimonial 3 -->
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "As someone with sensitive skin, I'm always cautious about trying new products. The Gentle Cleansing Oil is amazing - it removes makeup completely without irritating my skin. Will definitely repurchase!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="https://randomuser.me/api/portraits/women/33.jpg" alt="Sana Malik">
                        </div>
                        <div class="author-info">
                            <h4>Sana Malik</h4>
                            <p>Islamabad, Pakistan</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Contact Us</h2>
                <p>We're here to help you with any questions about our products.</p>
            </div>
            
            <div class="footer-container">
                <div class="footer-col">
                    <h3>Headquarters</h3>
                    <p>Memon Goth, Malir<br>Karachi, Pakistan</p>
                    <p><i class="fas fa-phone"></i> 0313-2255595</p>
                    <p><i class="fas fa-envelope"></i> info@glamourcosmetics.pk</p>
                </div>
                
                <div class="footer-col">
                    <h3>Customer Support</h3>
                    <p>24/7 Support Available</p>
                    <p><i class="fas fa-phone"></i> 021-1234567</p>
                    <p><i class="fas fa-envelope"></i> support@glamourcosmetics.pk</p>
                </div>
                
                <div class="footer-col">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#skincare">Skincare</a></li>
                        <li><a href="#makeup">Makeup</a></li>
                        <li><a href="#bestsellers">Bestsellers</a></li>
                        <li><a href="#new-arrivals">New Arrivals</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Follow Us</h3>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                    <p>Stay updated with our latest products and offers.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-bottom">
                <p>&copy; 2023 Glamour Cosmetics. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Shopping Cart -->
    <div class="cart-overlay">
        <div class="cart-container">
            <div class="cart-header">
                <h3>Your Cart</h3>
                <button class="close-cart">&times;</button>
            </div>
            
            <div class="cart-items">
                <!-- Cart items will be added here dynamically -->
            </div>
            
            <div class="cart-total">
                <h4>Total: <span>Rs 0</span></h4>
            </div>
            
            <button class="checkout-btn">Proceed to Checkout</button>
        </div>
    </div>

    <!-- Admin Controls -->
    <div class="admin-controls">
        <div class="admin-btn">
            <i class="fas fa-cog"></i>
        </div>
        <div class="admin-panel">
            <h3>Admin Panel</h3>
            <p>Welcome, Owner!</p>
            <input type="file" id="image-upload" accept="image/*">
            <select id="product-select">
                <option value="">Select Product to Update</option>
                <option value="product1">Hydrating Face Moisturizer</option>
                <option value="product2">Vitamin C Serum</option>
                <option value="product3">Gentle Cleansing Oil</option>
                <option value="product4">Revitalizing Night Cream</option>
                <option value="product5">Velvet Matte Lipstick</option>
                <option value="product6">Natural Finish Foundation</option>
                <option value="product7">Nude Eyeshadow Palette</option>
                <option value="product8">Volume Boost Mascara</option>
                <option value="product9">Cream Blush Stick</option>
                <option value="product10">Hydrating Rose Face Mist</option>
            </select>
            <button class="btn" id="update-btn">Update Product Image</button>
        </div>
    </div>

    <script>
        // Mobile Menu Toggle
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const navLinks = document.querySelector('.nav-links');
        
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            mobileMenuBtn.innerHTML = navLinks.classList.contains('active') ? 
                '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
        });
        
        // Shopping Cart Functionality
        const cartBtn = document.querySelector('.cart-btn');
        const cartOverlay = document.querySelector('.cart-overlay');
        const closeCart = document.querySelector('.close-cart');
        const addToCartBtns = document.querySelectorAll('.add-to-cart');
        
        cartBtn.addEventListener('click', () => {
            cartOverlay.style.display = 'flex';
        });
        
        closeCart.addEventListener('click', () => {
            cartOverlay.style.display = 'none';
        });
        
        // Sample cart functionality
        addToCartBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                const productCard = btn.closest('.product-card');
                const productName = productCard.querySelector('.product-name').textContent;
                const productPrice = productCard.querySelector('.current-price').textContent;
                const productImg = productCard.querySelector('.product-image img').src;
                
                // In a real app, you would add this to a cart array and update the UI accordingly
                alert(`${productName} added to cart!`);
            });
        });
        
        // Admin Panel Toggle
        const adminBtn = document.querySelector('.admin-btn');
        const adminPanel = document.querySelector('.admin-panel');
        
        adminBtn.addEventListener('click', () => {
            adminPanel.style.display = adminPanel.style.display === 'block' ? 'none' : 'block';
        });
        
        // Admin Image Update Functionality
        const imageUpload = document.getElementById('image-upload');
        const productSelect = document.getElementById('product-select');
        const updateBtn = document.getElementById('update-btn');
        
        updateBtn.addEventListener('click', () => {
            if (!productSelect.value) {
                alert('Please select a product first');
                return;
            }
            
            if (!imageUpload.files[0]) {
                alert('Please select an image first');
                return;
            }
            
            const reader = new FileReader();
            reader.onload = function(e) {
                // In a real app, you would upload this to a server
                // For this demo, we'll just show a success message
                alert(`Image for ${productSelect.options[productSelect.selectedIndex].text} updated successfully!`);
            }
            reader.readAsDataURL(imageUpload.files[0]);
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 70,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    if (navLinks.classList.contains('active')) {
                        navLinks.classList.remove('active');
                        mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
                    }
                }
            });
        });
    </script>
</body>
</html>
