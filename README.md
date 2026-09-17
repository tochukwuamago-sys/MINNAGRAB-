<!doctype html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>MinnaGrab</title>

<style>
:root{
  --g:#087443;
  --o:#ff8500;
  --ink:#173b2a;
  --muted:#6e7c74;
  --bg:#f6f9f7
}

*{
  box-sizing:border-box
}

body{
  margin:0;
  font-family:Arial,sans-serif;
  background:var(--bg);
  color:var(--ink)
}

.nav{
  height:72px;
  background:#fff;
  border-bottom:1px solid #e5ece7;
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0 7%;
  position:sticky;
  top:0;
  z-index:3
}

.logo{
  font-weight:900;
  font-size:27px
}

.logo span{
  color:var(--o)
}

.navlinks{
  display:flex;
  gap:25px
}

.navlinks a{
  color:#43544b;
  text-decoration:none;
  font-size:14px
}

.cart{
  border:0;
  background:#eef8f2;
  color:var(--g);
  padding:11px 16px;
  border-radius:12px;
  font-weight:800;
  cursor:pointer
}

.hero{
  padding:65px 7%;
  background:linear-gradient(135deg,#eaf8f0,#fff8ef);
  display:grid;
  grid-template-columns:1.2fr .8fr;
  gap:35px;
  align-items:center
}

.hero h1{
  font-size:52px;
  line-height:1.02;
  margin:0 0 16px;
  letter-spacing:-2px
}

.hero h1 span{
  color:var(--g)
}

.hero p{
  color:var(--muted);
  font-size:17px;
  line-height:1.6;
  max-width:580px
}

.search{
  display:flex;
  background:#fff;
  border:1px solid #e5ece7;
  border-radius:15px;
  padding:6px;
  max-width:600px;
  margin-top:25px
}

.search input{
  flex:1;
  border:0;
  outline:0;
  padding:14px
}

.search button,
.primary{
  border:0;
  background:var(--g);
  color:#fff;
  padding:13px 22px;
  border-radius:11px;
  font-weight:800;
  cursor:pointer
}

.hero-art{
  min-height:280px;
  border-radius:30px;
  background:linear-gradient(145deg,#087443,#13a15b);
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:145px
}

.section{
  padding:45px 7%
}

.section h2{
  font-size:28px
}

.categories,
.stores{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:16px
}

.cat,
.store{
  background:#fff;
  border:1px solid #e5ece7;
  border-radius:18px
}

.cat{
  padding:24px 15px;
  text-align:center;
  cursor:pointer
}

.cat .icon{
  font-size:38px
}

.cat b{
  display:block;
  margin-top:10px
}

.cat small,
.store p{
  color:var(--muted)
}

.store{
  overflow:hidden
}

.storeimg{
  height:145px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:65px;
  background:#edf6f0
}

.storebody{
  padding:15px
}

.storebody h3{
  margin:0 0 7px
}

.productrow{
  display:flex;
  justify-content:space-between;
  align-items:center
}

.price{
  font-weight:900;
  color:var(--g)
}

.add{
  border:0;
  background:#eef8f2;
  color:var(--g);
  border-radius:9px;
  padding:7px 10px;
  font-weight:800;
  cursor:pointer
}

.footer{
  background:#103b28;
  color:#dceee4;
  padding:38px 7%;
  display:flex;
  justify-content:space-between
}

.toast{
  position:fixed;
  right:22px;
  bottom:22px;
  background:#173b2a;
  color:#fff;
  padding:14px 18px;
  border-radius:12px;
  display:none;
  z-index:5
}

@media(max-width:850px){
  .hero{
    grid-template-columns:1fr
  }

  .hero h1{
    font-size:40px
  }

  .categories,
  .stores{
    grid-template-columns:repeat(2,1fr)
  }

  .navlinks{
    display:none
  }
}

@media(max-width:500px){
  .hero{
    padding:45px 5%
  }

  .section{
    padding:35px 5%
  }

  .categories,
  .stores{
    grid-template-columns:1fr 1fr
  }
}
</style>
</head>

<body>

<nav class="nav">

<div class="logo">
Minna<span>Grab</span>
</div>

<div class="navlinks">
<a href="#categories">Categories</a>
<a href="#stores">Stores</a>
<a href="#how">How it works</a>
</div>

<button class="cart" onclick="showCart()">
🛒 Cart <span id="cartCount">0</span>
</button>

</nav>


<section class="hero">

<div>

<div style="font-weight:800;color:var(--g)">
📍 Serving Minna, Niger State
</div>

<h1>
Everything you need,
<br>
<span>delivered to you.</span>
</h1>

<p>
Order food, groceries, general products, gas and household essentials from local businesses in Minna.
</p>

<div class="search">

<input
id="search"
placeholder="Search for food, groceries, products..."
>

<button onclick="searchSite()">
Search
</button>

</div>

</div>

<div class="hero-art">
🛒
</div>

</section>


<section class="section" id="categories">

<h2>Shop by category</h2>

<div class="categories">

<div class="cat" onclick="filter('Food')">
<div class="icon">🍔</div>
<b>Food</b>
<small>Restaurants & meals</small>
</div>

<div class="cat" onclick="filter('Groceries')">
<div class="icon">🛒</div>
<b>Groceries</b>
<small>Daily essentials</small>
</div>

<div class="cat" onclick="filter('General')">
<div class="icon">📦</div>
<b>General Products</b>
<small>Shop anything</small>
</div>

<div class="cat" onclick="filter('Gas')">
<div class="icon">⛽</div>
<b>Gas & Household</b>
<small>Home essentials</small>
</div>

</div>

</section>


<section class="section" id="stores">

<h2>Popular stores in Minna</h2>

<div class="stores">

<div class="store">

<div class="storeimg">
🍗
</div>

<div class="storebody">

<h3>
Minna Food Hub
</h3>

<p>
Food • 25–40 min
</p>

<div class="productrow">

<span class="price">
₦3,500
</span>

<button
class="add"
onclick="addToCart('Jollof Rice')"
>
+ Add
</button>

</div>

</div>

</div>


<div class="store">

<div class="storeimg">
🥦
</div>

<div class="storebody">

<h3>
FreshMart Minna
</h3>

<p>
Groceries • 20–35 min
</p>

<div class="productrow">

<span class="price">
₦2,800
</span>

<button
class="add"
onclick="addToCart('Groceries')"
>
+ Add
</button>

</div>

</div>

</div>


<div class="store">

<div class="storeimg">
📱
</div>

<div class="storebody">

<h3>
Smart Accessories
</h3>

<p>
General • 30–45 min
</p>

<div class="productrow">

<span class="price">
₦7,500
</span>

<button
class="add"
onclick="addToCart('Phone Accessory')"
>
+ Add
</button>

</div>

</div>

</div>


<div class="store">

<div class="storeimg">
🧯
</div>

<div class="storebody">

<h3>
Home & Gas Store
</h3>

<p>
Gas & Household • 30–50 min
</p>

<div class="productrow">

<span class="price">
₦18,000
</span>

<button
class="add"
onclick="addToCart('Household Item')"
>
+ Add
</button>

</div>

</div>

</div>

</div>

</section>


<section class="section" id="how" style="background:#fff">

<h2>
How MinnaGrab works
</h2>

<div class="categories">

<div class="cat">
<div class="icon">1️⃣</div>
<b>Choose a store</b>
<small>Browse local vendors</small>
</div>

<div class="cat">
<div class="icon">2️⃣</div>
<b>Add to cart</b>
<small>Select what you need</small>
</div>

<div class="cat">
<div class="icon">3️⃣</div>
<b>Place your order</b>
<small>Confirm your address</small>
</div>

<div class="cat">
<div class="icon">4️⃣</div>
<b>Get delivery</b>
<small>Track your rider</small>
</div>

</div>

</section>


<footer class="footer">

<div>

<div class="logo" style="color:#fff">
Minna<span>Grab</span>
</div>

<small>
Shop • Order • We Deliver
</small>

</div>

<small>
© 2026 MinnaGrab — Demo
</small>

</footer>


<div class="toast" id="toast"></div>


<script>

let count = 0;

function addToCart(x){

count++;

document.getElementById('cartCount').textContent = count;

toast(x + ' added to cart');

}

function showCart(){

toast(
count
?
'Your cart has ' + count + ' item(s).'
:
'Your cart is empty.'
);

}

function toast(x){

let t = document.getElementById('toast');

t.textContent = x;

t.style.display = 'block';

setTimeout(
() => t.style.display = 'none',
2200
);

}

function searchSite(){

let q =
document.getElementById('search')
.value
.trim();

toast(
q
?
'Searching for "' + q + '"...'
:
'Type something to search.'
);

}

function filter(x){

toast(
'Showing ' + x + ' stores...'
);

document
.getElementById('stores')
.scrollIntoView({
behavior:'smooth'
});

}

</script>

</body>
</html>
