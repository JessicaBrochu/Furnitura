<template>
  <div class="wrapper">
    <nav>
      <div class="logo">
        <a href="#"><img src="../src/assets/logo.svg" alt="logo"></a>
      </div>
      <div class="navigation">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/contact">Contact</router-link>
      </div>
    </nav>
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
  height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav a {
  padding-right: 50px;
  font-weight: 400;
  color: #2A2B30;
  text-decoration: none;

}

nav a.router-link-exact-active {
  color: #2A2B30;
}
</style>
