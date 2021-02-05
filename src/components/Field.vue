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
      return "width: " + (100 - 1 * this.content.length)/this.content.length + "%;";
    }
  }
};
</script>

<style lang="scss" scoped>

.container {
  width: 100%;
}

.cell {
  aspect-ratio: 1/1;
  background: #abe68e;
  border: 3px solid #28a745;
  border-radius: 7px;
  margin: 0 0.5% 0.5% 0;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
