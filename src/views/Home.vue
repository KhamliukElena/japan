<template>
  <div>
    <div class="home">
    <h2>Rules</h2>
    <p>
      Nonograms, also known as Hanjie, Picross or Griddlers, are picture logic puzzles in which cells in a grid must be colored or left blank according to numbers at the side of the grid to reveal a hidden picture. In this puzzle type, the numbers are a form of discrete tomography that measures how many unbroken lines of filled-in squares there are in any given row or column. For example, a clue of "4 8 3" would mean there are sets of four, eight, and three filled squares, in that order, with at least one blank square between successive groups.
    </p>
    <router-link to="/game"><button class="btn btn-success">Start game</button></router-link>
  </div>
  <nav class="navbar fixed-bottom">
    <div class="ml-auto">Authors of Icons: <a href="https://www.flaticon.com/ru/authors/icongeek26" title="Icongeek26">Icongeek26</a>,  
    <a href="https://www.flaticon.com/authors/google" title="Google">Google</a>, 
    <a href="https://www.freepik.com" title="Freepik">Freepik</a>
    from <a href="https://www.flaticon.com/ru/" title="Flaticon">www.flaticon.com</a><br>
    <a href="http://gambiter.com/puzzle/Nonogram.html">Rules source</a></div>
  </nav>
  </div>
</template>

<style scoped>
.ml-auto {
  font-size: 0.8em;
}

.home {
  padding: 7% 7% 2% 10%;
}

p {
  text-align: justify;
}
</style>