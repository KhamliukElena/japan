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
</template>

<style lang="scss">
.navbar-brand {
  font-size: 1.5em;
  color: #fafaf1;
  text-shadow: 1px 1px 3px #2e302d;
}

.brand {
  margin-left: 5px;
}

router-link {
  text-decoration: none;
}

a {
  color: #28a745;
}

a:hover, .navbar-brand:hover {
  color: #464643;
}

img {
  height: 40px;
}

body {
  background: #fafaf1;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
/**** Small devices**** */
@media (max-width: 575.98px) {
  .navbar-brand {
    font-size: 1.4em;
  }
}
@media (max-width: 350px) {
  .navbar-brand {
    font-size: 1.1em;
  }
}
</style>
