<template>
  <div class="game">
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
    return { content: [ [1, 0, 1, 0],
            [0, 1, 0, 0],
            [1, 0, 1, 0],
            [1, 0, 1, 0]
    ]};
  },
  methods: {
    //there are methods for game
  }
}
</script>

<style lang="scss">
.game {
  padding-top: 1.4%;
  padding-bottom: 1.65%;
}
</style>