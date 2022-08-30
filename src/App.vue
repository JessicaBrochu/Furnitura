<template>
  <div class="wrapper">
    <nav class="header">
      <div class="logo">
        <router-link to="/"><img src="../src/assets/logo.svg" alt="logo"></router-link>
      </div>
      <div class="navigation">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/contact">Contact</router-link>
      </div>
    </nav>
    <div class="hero">
      <div class="hero_title">
        <h1 class="hero_buy_and_sell">BUY AND SELL</h1>
        <h1 class="hero_used_furniture">USED FURNITURES</h1>
        <h1 class="hero_safely">SAFELY</h1>
      </div>
      <div class="img01">
        <img src="../src/assets/img01.jpg" alt="">
      </div>
      <div class="img02">
        <img src="../src/assets/img02.jpg" alt="">
      </div>
      <div class="img03">
        <img src="../src/assets/img03.jpg" alt="">
      </div>
      <div class="img04">
        <img src="../src/assets/img04.jpg" alt="">
      </div>
    </div>
    <router-view/>
  </div>
</template>

<style>

#app {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2A2B30;
}

.wrapper{
  max-width: 1440px;
  width: 100%;
  margin: 0 auto;
}

nav {
  height: 75px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav a {
  font-weight: 400;
  color: #2A2B30;
  text-decoration: none;
}

.navigation a{
    margin-left: 50px;
}

nav a.router-link-exact-active {
  color: #2A2B30;
}

.hero{
  position: relative;
  display: grid;
  gap: 16px;
  grid-template-areas: 
  "img01 img02 img03"
  "img01 img04 img04";
}

.hero_buy_and_sell{
  font-size: 65px;
  margin: 10px 0;
}

.hero_used_furniture{
  font-size: 50px;
  margin: 0;
}

.hero_safely{
  font-size: 122px;
  margin: 0;
}

.hero_title{
  z-index: 1;
  color: #fff;
  position: absolute;
  top: 0;
  transform: translateY(50%);
  left: 50px;
}

.img01{
  grid-area: img01;
  position: relative;
}
.img01::after{
  content: "";
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6);
}
.img01 img{
  object-fit: cover;
}
.img02{
  grid-area: img02;
}
.img03{
  grid-area: img03;
}
.img04{
  grid-area: img04;
}
img{
  width: 100%;
  height: 100%;
}

</style>
