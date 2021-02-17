<template>
  <div class="game">
    <div class="container-fluid">
      <div class="row">
        <div class="col-md-1"></div>
        <div class="col-md-11"><Field v-bind:content="content" 
                                      v-bind:cellsToFind="cellsToFind"/></div>
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
                        [0, 0, 1, 0],
    ]};
  },
  computed: {
    cellsToFind: function () {
      let ones = 0;
      for (let i=0; i<this.content.length; i++) {
        for (let j=0; j<this.content.length; j++) {
          if (this.content[i][j] == 1)  {
            ones++;
          }
        }
      }
      return ones;
    }
  }
}
</script>

<style lang="scss">
.game {
  padding: 0.7% 5%;
}
</style>