<template>
  <!--Main navbar-->
  <nav class="navbar bg-success">
    <div class="container-fluid">
      <router-link to="/" class="navbar-brand text-light">
        <img src="./assets/1250641.svg" alt="logo" loading="lazy"/>
        <span class="brand">Welcome to Nonogram!</span></router-link>
    </div>
  </nav>
  <!--Content-->
  <router-view/>
  <!--footer-->
  <nav class="navbar fixed-bottom d-flex flex-row-reverse">
    <div class="p-2">Author of Icons: <a href="https://www.flaticon.com/ru/authors/icongeek26" title="Icongeek26">Icongeek26</a> from <a href="https://www.flaticon.com/ru/" title="Flaticon">www.flaticon.com</a></div>
  </nav>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.navbar-brand {
  font-size: 1.5em;
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
