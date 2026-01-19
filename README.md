<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>LUXE WEAR | Premium Clothing</title>

  <!-- GOOGLE FONT -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

  <!-- CSS -->
  <style>
    :root {
      --primary: #000;
      --secondary: #c59d5f;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: #fff;
      color: #000;
      overflow-x: hidden;
    }

    /* NAVBAR */
    header {
      position: fixed;
      top: 0;
      width: 100%;
      padding: 20px 60px;
      background: rgba(0,0,0,0.9);
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 999;
    }

    header h1 {
      color: #fff;
      letter-spacing: 2px;
    }

    header span {
      color: var(--secondary);
    }

    nav a {
      color: #fff;
      margin-left: 30px;
      text-decoration: none;
    }

    nav a:hover {
      color: var(--secondary);
    }

    /* HERO */
    .hero {
      height: 100vh;
      background: url('https://images.unsplash.com/photo-1521334884684-d80222895322') center/cover;
      display: flex;
      align-items: center;
      padding: 0 80px;
      color: #fff;
    }

    .hero h2 {
      font-size: 60px;
      margin-bottom: 20px;
    }

    .hero button {
      padding: 15px 40px;
      background: var(--secondary);
      border: none;
      cursor: pointer;
      font-weight: 600;
    }

    /* PRODUCTS */
    section {
      padding: 120px 80px;
    }

    .title {
      text-align: center;
      margin-bottom: 60px;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px,1fr));
      gap: 40px;
    }

    .product {
      position: relative;
      overflow: hidden;
      border-radius: 15px;
    }

    .product img {
      width: 100%;
      height: 400px;
      object-fit: cover;
      transition: 0.5s;
    }

    .product:hover img {
      transform: scale(1.1);
    }

    .info {
      position: absolute;
      inset: 0;
      background: rgba(0,0,0,0.7);
      color: #fff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      transform: translateY(100%);
      transition: 0.5s;
      gap: 10px;
    }

    .product:hover .info {
      transform: translateY(0);
    }

    .info button {
      padding: 10px 25px;
      background: var(--secondary);
      border: none;
      cursor: pointer;
    }

    /* CART */
    .cart {
      position: fixed;
      right: -400px;
      top: 0;
      width: 400px;
      height: 100vh;
      background: #111;
      color: #fff;
      padding: 30px;
      transition: 0.5s;
      z-index: 1000;
    }

    .cart.active {
      right: 0;
    }

    .cart-item {
      display: flex;
      justify-content: space-between;
      padding: 10px 0;
      border-bottom: 1px solid #333;
    }

    footer {
      background: #000;
      color: #aaa;
      text-align: center;
      padding: 40px;
    }
  </style>
</head>

<body>

  <header>
    <h1>LUXE<span>WEAR</span></h1>
    <nav>
      <a href="#">Home</a>
      <a href="#shop">Shop</a>
      <a href="#">About</a>
      <a href="#" onclick="toggleCart()">Cart (<span id="count">0</span>)</a>
    </nav>
  </header>

  <div class="hero">
    <div>
      <h2>Luxury Fashion<br>Redefined</h2>
      <p>Premium quality. Timeless style. Designed for elites.</p>
      <button>EXPLORE COLLECTION</button>
    </div>
  </div>

  <section id="shop">
    <div class="title">
      <h2>Featured Collection</h2>
    </div>

    <div class="grid">
      <div class="product">
        <img src="https://images.unsplash.com/photo-1512436991641-6745cdb1723f">
        <div class="info">
          <h3>Black Hoodie</h3>
          <p>PKR 4,500</p>
          <button onclick="add('Black Hoodie')">Add to Cart</button>
        </div>
      </div>

      <div class="product">
        <img src="https://images.unsplash.com/photo-1520975916090-3105956dac38">
        <div class="info">
          <h3>Denim Jacket</h3>
          <p>PKR 7,200</p>
          <button onclick="add('Denim Jacket')">Add to Cart</button>
        </div>
      </div>

      <div class="product">
        <img src="https://images.unsplash.com/photo-1526170375885-4d8ecf77b99f">
        <div class="info">
          <h3>Premium Shirt</h3>
          <p>PKR 3,800</p>
          <button onclick="add('Premium Shirt')">Add to Cart</button>
        </div>
      </div>
    </div>
  </section>

  <div class="cart" id="cart">
    <h2>Your Cart</h2>
    <div id="items"></div>
  </div>

  <footer>
    <p>© 2026 LUXEWEAR — Crafted with Style</p>
  </footer>

  <!-- JAVASCRIPT -->
  <script>
    let count = 0;
    const items = document.getElementById('items');
    const cart = document.getElementById('cart');

    function add(name) {
      count++;
      document.getElementById('count').innerText = count;

      const div = document.createElement('div');
      div.className = 'cart-item';
      div.innerHTML = `<span>${name}</span><span>✓</span>`;
      items.appendChild(div);
    }

    function toggleCart() {
      cart.classList.toggle('active');
    }
  </script>

</body>
</html>
