# sample

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cozy Collective</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --main-color: #4caf50;
            --hover-color: #388E3C;
            --background-color: #f5f7f2;
            --text-color: #333;
            --button-color: #66bb6a;
            --button-hover-color: #4caf50;
        }
        body {
            font-family: 'Montserrat', sans-serif;
            margin: 0;
            background-color: var(--background-color);
            color: var(--text-color);
            overflow-x: hidden;
        }
        #header {
            background-color: var(--main-color);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        #logo {
            font-family: 'Playfair Display', serif;
            font-size: 36px;
            font-weight: bold;
            letter-spacing: 2px;
            margin-bottom: 10px;
            animation: fadeIn 0.5s;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        #toggle-button {
            cursor: pointer;
            background-color: transparent;
            border: none;
            color: white;
            font-size: 28px;
            position: absolute;
            right: 20px;
            top: 15px;
        }
        #navbar {
            display: flex;
            justify-content: center;
            background-color: var(--hover-color);
            padding: 15px 0;
        }
        #navbar a {
            text-decoration: none;
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            margin: 0 10px;
            background: var(--button-color);
            transition: background-color 0.3s, transform 0.3s;
            font-weight: 700;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        #navbar a:hover {
            background-color: var(--hover-color);
            transform: translateY(-2px);
        }
        #search-bar {
            margin: 20px auto;
            display: flex;
            justify-content: center;
            width: 100%;
            max-width: 600px;
        }
        #search-input {
            padding: 10px;
            flex: 1;
            border: 2px solid var(--button-color);
            border-radius: 5px 0 0 5px;
            outline: none;
            transition: border-color 0.3s;
        }
        #search-input:focus {
            border-color: var(--hover-color);
        }
        #search-button {
            padding: 10px;
            border: none;
            background-color: var(--button-color);
            color: white;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        #search-button:hover {
            background-color: var(--hover-color);
        }
        #sidebar {
            display: none;
            flex-direction: column;
            background: var(--button-color);
            padding: 20px;
            width: 250px;
            position: fixed;
            top: 60px;
            right: -260px;
            transition: right 0.3s ease;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
            border-radius: 8px;
            z-index: 1000;
        }
        #sidebar.active {
            display: flex;
            right: 0;
        }
        #sidebar h2 {
            color: white;
            margin: 0 0 15px;
            text-align: center;
            font-weight: 700;
        }
        #sidebar a {
            color: white;
            margin: 5px 0;
            padding: 10px;
            border-radius: 5px;
            transition: background-color 0.3s;
            text-align: center;
        }
        #sidebar a:hover {
            background-color: var(--hover-color);
        }
        #content {
            padding: 20px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            width: calc(100% - 40px);
        }
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px;
            width: 100%;
        }
        .product {
            background: white;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            overflow: hidden;
            position: relative;
            cursor: pointer;
        }
        .product img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px 10px 0 0;
        }
        .product:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
        }
        h2 {
            color: var(--text-color);
            font-weight: 700;
            margin-bottom: 15px;
        }
        .category {
            display: none;
        }
        .category.active {
            display: block;
        }
        #follow-us {
            background-color: #e7f5e1;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            margin-top: 20px;
            width: 100%;
        }
        #follow-us h2 {
            color: var(--text-color);
        }
        #social-icons {
            display: flex;
            justify-content: center;
            margin-top: 10px;
        }
        .social-icon {
            margin: 0 10px;
            text-decoration: none;
            font-size: 28px;
            transition: color 0.3s;
            color: var(--text-color);
        }
        .social-icon:hover {
            color: var(--hover-color);
        }
        #footer {
            background-color: var(--main-color);
            color: white;
            text-align: center;
            padding: 15px;
            position: relative;
            margin-top: 20px;
        }
        .home-images {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 20px;
            width: 100%;
        }
        .home-images img {
            width: calc(33.33% - 20px);
            margin: 10px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
            transition: transform 0.3s;
        }
        .home-images img:hover {
            transform: scale(1.05);
        }
    </style>
</head>
<body>

<div id="header">
    <div id="logo">Cozy Collective</div>
    <button id="toggle-button" aria-label="Toggle sidebar">☰</button>
</div>

<div id="navbar">
    <a href="#" onclick="showCategory('home')">Home</a>
    <a href="#" onclick="showCategory('electronics')">Electronics</a>
    <a href="#" onclick="showCategory('clothing')">Clothing</a>
    <a href="#" onclick="showCategory('kitchen')">Home & Kitchen</a>
    <a href="#" onclick="showCategory('books')">Books</a>
    <a href="#" onclick="showCategory('toys')">Toys</a>
</div>

<div id="search-bar">
    <input type="text" id="search-input" placeholder="Search for products...">
    <button id="search-button" onclick="searchProducts()">Search</button>
</div>

<div id="sidebar" role="navigation" aria-label="Categories">
    <h2>Categories</h2>
    <a href="#" onclick="showCategory('electronics')">Electronics</a>
    <a href="#" onclick="showCategory('clothing')">Clothing</a>
    <a href="#" onclick="showCategory('kitchen')">Home & Kitchen</a>
    <a href="#" onclick="showCategory('books')">Books</a>
    <a href="#" onclick="showCategory('toys')">Toys</a>
</div>

<div id="content">
    <div class="category active" id="home">
        <h2>Welcome to Cozy Collective</h2>
        <p>Your one-stop shop for everything you need!</p>
        <div class="home-images">
            <img src="https://images.pexels.com/photos/4500259/pexels-photo-4500259.jpeg" alt="Electronics">
            <img src="https://images.pexels.com/photos/3764643/pexels-photo-3764643.jpeg" alt="Clothing">
            <img src="https://images.pexels.com/photos/3736765/pexels-photo-3736765.jpeg" alt="Kitchenware">
            <img src="https://images.pexels.com/photos/4050299/pexels-photo-4050299.jpeg" alt="Books">
            <img src="https://images.pexels.com/photos/3861440/pexels-photo-3861440.jpeg" alt="Toys">
            <img src="https://images.pexels.com/photos/4050298/pexels-photo-4050298.jpeg" alt="Appliances">
        </div>
    </div>

    <div class="category" id="electronics">
        <h2>Welcome to the Electronics Section!</h2>
        <p>Here you can find all sorts of electronic devices, gadgets, and accessories.</p>
    </div>

    <div class="category" id="clothing">
        <h2>Welcome to the Clothing Section!</h2>
        <p>Explore our wide range of fashionable clothing options.</p>
    </div>

    <div class="category" id="kitchen">
        <h2>Welcome to the Home & Kitchen Section!</h2>
        <p>Find everything you need for your home and kitchen.</p>
    </div>

    <div class="category" id="books">
        <h2>Welcome to the Books Section!</h2>
        <p>Discover our collection of books across various genres.</p>
    </div>

    <div class="category" id="toys">
        <h2>Welcome to the Toys Section!</h2>
        <p>Check out our selection of toys for kids of all ages.</p>
    </div>

    <div class="product-grid">
        <div class="product" onclick="redirectTo('Product 1')">
            <img src="https://images.pexels.com/photos/4050298/pexels-photo-4050298.jpeg" alt="Product 1">
            <h3>Product 1</h3>
            <p>Description of product 1.</p>
            <p>Price: $19.99</p>
        </div>
        <div class="product" onclick="redirectTo('Product 2')">
            <img src="https://images.pexels.com/photos/4500259/pexels-photo-4500259.jpeg" alt="Product 2">
            <h3>Product 2</h3>
            <p>Description of product 2.</p>
            <p>Price: $29.99</p>
        </div>
        <div class="product" onclick="redirectTo('Product 3')">
            <img src="https://images.pexels.com/photos/3861440/pexels-photo-3861440.jpeg" alt="Product 3">
            <h3>Product 3</h3>
            <p>Description of product 3.</p>
            <p>Price: $39.99</p>
        </div>
        <div class="product" onclick="redirectTo('Product 4')">
            <img src="https://images.pexels.com/photos/3764643/pexels-photo-3764643.jpeg" alt="Product 4">
            <h3>Product 4</h3>
            <p>Description of product 4.</p>
            <p>Price: $49.99</p>
        </div>
        <div class="product" onclick="redirectTo('Product 5')">
            <img src="https://images.pexels.com/photos/4050299/pexels-photo-4050299.jpeg" alt="Product 5">
            <h3>Product 5</h3>
            <p>Description of product 5.</p>
            <p>Price: $59.99</p>
        </div>
        <div class="product" onclick="redirectTo('Product 6')">
            <img src="https://images.pexels.com/photos/3736765/pexels-photo-3736765.jpeg" alt="Product 6">
            <h3>Product 6</h3>
            <p>Description of product 6.</p>
            <p>Price: $69.99</p>
        </div>
    </div>
</div>

<div id="follow-us">
    <h2>Follow Us</h2>
    <div id="social-icons">
        <a href="https://www.facebook.com" class="social-icon" target="_blank" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
        <a href="https://www.twitter.com" class="social-icon" target="_blank" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
        <a href="https://www.instagram.com" class="social-icon" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
        <a href="https://www.youtube.com" class="social-icon" target="_blank" aria-label="YouTube"><i class="fab fa-youtube"></i></a>
    </div>
</div>

<div id="footer">
    &copy; 2024 Cozy Collective. All rights reserved.
</div>

<script>
    const toggleButton = document.getElementById('toggle-button');
    const sidebar = document.getElementById('sidebar');

    toggleButton.addEventListener('click', () => {
        sidebar.classList.toggle('active');
    });

    function showCategory(category) {
        const categories = document.querySelectorAll('.category');
        categories.forEach(cat => cat.classList.remove('active'));
        document.getElementById(category).classList.add('active');
        closeSidebar();  // Close sidebar when category is selected
    }

    function closeSidebar() {
        sidebar.classList.remove('active');
    }

    function redirectTo(productName) {
        alert(`Redirecting to ${productName} page...`);
        // Implement actual redirection logic here
    }

    function searchProducts() {
        const query = document.getElementById('search-input').value.toLowerCase();
        const products = document.querySelectorAll('.product');
        products.forEach(product => {
            const productName = product.querySelector('h3').innerText.toLowerCase();
            product.style.display = productName.includes(query) ? 'block' : 'none';
        });
    }

    document.addEventListener('click', function(event) {
        if (!sidebar.contains(event.target) && !toggleButton.contains(event.target)) {
            closeSidebar();
        }
    });
</script>

</body>
</html>
