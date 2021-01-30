<template>
  <div id="nav">
    <h1>Welcome to Nonogram!</h1>
    <router-link to="/">Home</router-link> 
    <router-link to="/game">Start game</router-link>
  </div>
  <router-view/>
</template>

<style lang="scss">
* {
  font: 15pt sans-serif;
  margin: 0;
  padding: 0;
}
</style>
