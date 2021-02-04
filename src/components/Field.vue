<template>
  <div class="container">
    <div class="container-fluid">
      <div v-for="row in content.length" :key="row" class="row">
        <div v-for="col in content.length" :key="col" class="cell"
          v-bind:style="sellSize">
          Cell {{row.toString() + " " + col.toString() }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Field',
  props: {
    content: {
      type: Array
    }
  },
  computed: {
    sellSize: function() {
      return "width: " + 100/this.content.length + "%;";
    }
  }
};
</script>

<style lang="scss" scoped>

.container, .cell {
  border: 3px solid black;
}

.container {
  width: 100%;
  aspect-ratio: 1/1;
}

.cell {
  aspect-ratio: 1/1;
  background: #abe68e;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
