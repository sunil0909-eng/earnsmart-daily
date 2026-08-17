08.17 7:19 AM
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>StyleMart - Fashion Shopping</title>
<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}
body{
    font-family:Arial, sans-serif;
    background:#f7f7f7;
    color:#222;
}
/* HEADER */
header{
    background:#fff;
    padding:15px 5%;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:20px;
    position:sticky;
    top:0;
    z-index:1000;
    box-shadow:0 2px 10px rgba(0,0,0,.08);
}
.logo{
    font-size:25px;
    font-weight:bold;
    color:#e91e63;
}
.search{
    flex:1;
    max-width:550px;
}
.search input{
    width:100%;
    padding:12px 18px;
    border:1px solid #ddd;
    border-radius:25px;
    outline:none;
    font-size:15px;
}
/* HERO */
.hero{
    margin:20px 5%;
    padding:45px 30px;
    border-radius:18px;
    background:linear-gradient(135deg,#ff4081,#e91e63);
    color:white;
}
.hero h1{
    font-size:38px;
    margin-bottom:10px;
}
.hero p{
    font-size:17px;
    margin-bottom:20px;
}
.hero button{
    border:none;
    padding:12px 25px;
    border-radius:25px;
    background:white;
    color:#e91e63;
    font-weight:bold;
    cursor:pointer;
}
/* SECTION */
section{
    padding:15px 5%;
}
.section-title{
    margin-bottom:18px;
    font-size:24px;
}
/* CATEGORIES */
.categories{
    display:flex;
    gap:12px;
    overflow-x:auto;
    padding-bottom:10px;
}
.category{
    min-width:110px;
    background:white;
    padding:18px 10px;
    border-radius:12px;
    text-align:center;
    cursor:pointer;
    box-shadow:0 2px 8px rgba(0,0,0,.06);
}
.category span{
    display:block;
    font-size:30px;
    margin-bottom:8px;
}
/* PRODUCTS */
.products{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:18px;
}
.product{
    background:white;
    border-radius:14px;
    overflow:hidden;
    box-shadow:0 2px 10px rgba(0,0,0,.07);
}
.product img{
    width:100%;
    height:240px;
    object-fit:cover;
}
.product-info{
    padding:13px;
}
.product-name{
    font-size:15px;
    margin-bottom:7px;
}
.rating{
    font-size:13px;
    margin-bottom:8px;
}
.price{
    font-size:19px;
    font-weight:bold;
}
.old-price{
    color:#999;
    text-decoration:line-through;
    font-size:13px;
    margin-left:5px;
}
.discount{
    color:#16a34a;
    font-size:13px;
    margin-left:5px;
}
.buy{
    width:100%;
    border:none;
    padding:11px;
    margin-top:10px;
    border-radius:8px;
    background:#e91e63;
    color:white;
    font-weight:bold;
    cursor:pointer;
}
.buy:hover{
    opacity:.9;
}
/* FOOTER */
footer{
    margin-top:35px;
    padding:30px 5%;
    background:#222;
    color:white;
    text-align:center;
}
footer p{
    margin:8px 0;
    color:#ccc;
}
/* MOBILE */
@media(max-width:800px){
    header{
        flex-wrap:wrap;
    }
    .logo{
        width:100%;
        text-align:center;
    }
    .search{
        max-width:none;
        width:100%;
    }
    .hero{
        margin:15px 3%;
        padding:30px 20px;
    }
    .hero h1{
        font-size:28px;
    }
    .products{
        grid-template-columns:repeat(2,1fr);
        gap:12px;
    }
    .product img{
        height:190px;
    }
    .product-info{
        padding:10px;
    }
    .section-title{
        font-size:20px;
    }
}
</style>
</head>
<body>
<!-- HEADER -->
<header>
    <div class="logo">
        StyleMart
    </div>
    <div class="search">
        <input
            type="text"
            id="searchInput"
            placeholder="Search for dresses, kurtis, sarees..."
            onkeyup="searchProducts()"
        >
    </div>
</header>
<!-- HERO -->
<div class="hero">
    <h1>Discover Your Style</h1>
    <p>
        Trendy fashion at amazing prices.
        Find your perfect look with StyleMart.
    </p>
    <button onclick="scrollToProducts()">
        Shop Now
    </button>
</div>
<!-- CATEGORIES -->
<section>
    <h2 class="section-title">
        Shop By Category
    </h2>
    <div class="categories">
        <div class="category">
            <span></span>
            Dresses
        </div>
        <div class="category">
            <span>🥻</span>
            Sarees
        </div>
        <div class="category">
            <span></span>
            Kurtis
        </div>
        <div class="category">
            <span></span>
            Men's Wear
        </div>
        <div class="category">
            <span>🧒</span>
            Kids
        </div>
        <div class="category">
            <span></span>
            Footwear
        </div>
    </div>
</section>
<!-- PRODUCTS -->
<section id="productsSection">
    <h2 class="section-title">
         Trending Products
    </h2>
    <div class="products" id="productList">
        <!-- PRODUCT 1 -->
        <div class="product" data-name="women floral dress">
            <img
                src="https://images.unsplash.com/photo-1595777457583-95e059d581b8?auto=format&fit=crop&w=600&q=80"
                alt="Women's Floral Dress"
            >
            <div class="product-info">
                <div class="product-name">
                    Women's Floral Summer Dress
                </div>
                <div class="rating">
                    ⭐ 4.5
                </div>
                <div>
                    <span class="price">₹499</span>
                    <span class="old-price">₹999</span>
                    <span class="discount">50% OFF</span>
                </div>
                <button
                    class="buy"
                    onclick="buyProduct('DEMO_LINK_1')"
                >
                    Buy Now
                </button>
            </div>
        </div>
        <!-- PRODUCT 2 -->
        <div class="product" data-name="women kurti">
            <img
                src="https://images.unsplash.com/photo-1610030469983-98e550d6193c?auto=format&fit=crop&w=600&q=80"
                alt="Women's Kurti"
            >
            <div class="product-info">
                <div class="product-name">
                    Women's Stylish Printed Kurti
                </div>
                <div class="rating">
                    ⭐ 4.3
                </div>
                <div>
                    <span class="price">₹399</span>
                    <span class="old-price">₹799</span>
                    <span class="discount">50% OFF</span>
                </div>
                <button
                    class="buy"
                    onclick="buyProduct('DEMO_LINK_2')"
                >
                    Buy Now
                </button>
            </div>
        </div>
        <!-- PRODUCT 3 -->
        <div class="product" data-name="women saree">
            <img
                src="https://images.unsplash.com/photo-1617627143750-d86bc21e42bb?auto=format&fit=crop&w=600&q=80"
                alt="Women's Saree"
            >
            <div class="product-info">
                <div class="product-name">
                    Elegant Women's Saree
                </div>
                <div class="rating">
                    ⭐ 4.6
                </div>
                <div>
                    <span class="price">₹699</span>
                    <span class="old-price">₹1,299</span>
                    <span class="discount">46% OFF</span>
                </div>
                <button
                    class="buy"
                    onclick="buyProduct('DEMO_LINK_3')"
                >
                    Buy Now
                </button>
            </div>
        </div>
        <!-- PRODUCT 4 -->
        <div class="product" data-name="men tshirt">
            <img
                src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?auto=format&fit=crop&w=600&q=80"
                alt="Men T-Shirt"
            >
            <div class="product-info">
                <div class="product-name">
                    Men's Casual Cotton T-Shirt
                </div>
                <div class="rating">
                    ⭐ 4.4
                </div>
                <div>
                    <span class="price">₹299</span>
                    <span class="old-price">₹599</span>
                    <span class="discount">50% OFF</span>
                </div>
                <button
                    class="buy"
                    onclick="buyProduct('DEMO_LINK_4')"
                >
                    Buy Now
                </button>
            </div>
        </div>
    </div>
</section>
<!-- FOOTER -->
<footer>
    <h2>StyleMart</h2>
    <p>
        Discover fashion. Discover your style.
    </p>
    <p>
        © 2026 StyleMart. All rights reserved.
    </p>
</footer>
<script>
/* SEARCH */
function searchProducts(){
    let input =
        document
        .getElementById("searchInput")
        .value
        .toLowerCase();
    let products =
        document.querySelectorAll(".product");
    products.forEach(function(product){
        let name =
            product
            .getAttribute("data-name")
            .toLowerCase();
        if(name.includes(input)){
            product.style.display = "";
        }else{
            product.style.display = "none";
        }
    });
}
/* SHOP NOW */
function scrollToProducts(){
    document
    .getElementById("productsSection")
    .scrollIntoView({
        behavior:"smooth"
    });
}
/* BUY NOW */
function buyProduct(link){
    if(link.startsWith("http")){
        window.open(link, "_blank");
    }else{
        alert(
            "Affiliate product link will be added here."
        );
    }
}
</script>
</body>
</html>

