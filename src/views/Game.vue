<template>
  <div class="game">
    <h2>There will be a game</h2>
    <div class="container">
      <div class="row">
        <div class="col-md-2"><!--Left bar--></div>
        <div class="col-md-9"><Field v-bind:content="content" /></div>
        <div class="col-md-1"><!--Right bar--></div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Field from '@/components/Field.vue'

export default {
  name: 'Game',
  components: {
    Field
  },
  data() {
    return { content: [ [1, 0, 1],
            [0, 1, 0],
            [1, 0, 1]
    ]};
  },
  methods: {
    //there are methods for game
  }
}
</script>

<style>
  div[class="row"], div[class="col-md-1"], div[class="col-md-2"], div[class="col-md-9"] {
    border: 2px solid black;
  }
</style>