<template>
  <div>
    <!-- Hero Section -->
    <div class="hero">
      <div class="hero-content">
        <h1 class="hero-title">Selamat Datang di VIIShop</h1>
        <p class="hero-description">
          Temukan Produk Natal Terbaik Untuk Suasana yang Tak Terlupakan
        </p>
        <NuxtLink to="/product" class="cta-button"> Lihat Produk </NuxtLink>
      </div>
    </div>

    <div class="about">
      <div class="about-content">
        <h2 class="about-title">Tentang Kami</h2>
        <p class="about-description">
          VIIShop hadir untuk menyediakan produk berkualitas tinggi yang akan
          membuat perayaan Natal Anda menjadi istimewa. Dengan koleksi terbaik
          kami, kami bertujuan memberikan pengalaman belanja yang menyenangkan
          dan memuaskan.
        </p>
      </div>
    </div>

    <div class="featured-products">
      <h2 class="section-title">Produk Unggulan</h2>
      <div class="product-list">
        <div class="product">
          <div class="product-content">
            <img src="@/public/images/product12.jpg" alt="Product 1" />
            <h3 class="product-title"></h3>
            <p class="product-description">best seller1</p>
          </div>
        </div>
        <div class="product">
          <div class="product-content">
            <img src="@/public/images/product13.jpg" alt="Product 2" />
            <h3 class="product-title"></h3>
            <p class="product-description">best seller2</p>
          </div>
        </div>
        <div class="product">
          <div class="product-content">
            <img src="@/public/images/product17.jpg" alt="Product sjjs" />
            <h3 class="product-title"></h3>
            <p class="product-description">best seller3</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.hero {
  background: url("images/background.jpg") center/cover no-repeat;
  height: 80vh;
  display: flex;
  align-items: center;
  color: #fff;
}

.hero-content {
  text-align: center;
}

.hero-title {
  font-size: 3em;
  margin-bottom: 20px;
}

.hero-description {
  font-size: 1.5em;
  margin-bottom: 30px;
}

.cta-button {
  background-color: #007bff;
  color: #fff;
  padding: 15px 30px;
  font-size: 1.2em;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.cta-button:hover {
  background-color: #0056b3;
}

.about {
  background-color: #f8f9fa;
  padding: 60px 0;
}

.about-title {
  font-size: 2.5em;
  margin-bottom: 20px;
  color: #333;
}

.about-description {
  font-size: 1.2em;
  color: #555;
  line-height: 1.5;
}

.featured-products {
  text-align: center;
  padding: 60px 0;
}

.section-title {
  font-size: 2.5em;
  margin-bottom: 40px;
  color: #333;
}

.product-list {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  gap: 20px;
}

.product {
  text-align: center;
}

.product-content {
  position: relative;
}

.product img {
  max-width: 100%;
  max-height: 150px;
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.product-title,
.product-description {
  position: absolute;
  left: 0;
  right: 0;
  margin: 0;
  padding: 10px;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 0 0 8px 8px;
}

.product-title {
  font-size: 1.8em;
  color: #333;
}

.product-description {
  font-size: 1.2em;
  color: #555;
}
</style>
