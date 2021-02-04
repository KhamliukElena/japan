<template>
  <!--Main navbar-->
  <nav class="navbar bg-success">
    <div class="container-fluid">
      <router-link to="/" class="navbar-brand">
        <img src="./assets/1250641.svg" alt="logo" loading="lazy"/>
        <span class="brand">Welcome to Nonogram!</span></router-link>
    </div>
  </nav>
  <!--Content-->
  <router-view/>
  <!--footer-->
  <div class="text-right">Author of Icons: <a href="https://www.flaticon.com/ru/authors/icongeek26" title="Icongeek26">Icongeek26</a> from <a href="https://www.flaticon.com/ru/" title="Flaticon">www.flaticon.com</a></div>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: #fafaf1;
}
.navbar-brand {
  font-size: 1.5em;
  color: #fafaf1;
}
img {
  height: 40px;
}
.brand {
  margin-left: 5px;
}
router-link {
  text-decoration: none;
}
</style>
