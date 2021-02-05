<template>
  <div class="container">
    <div class="container-fluid">
      <div v-for="row in content.length" :key="row" class="row">
        <div v-for="col in content.length" :key="col" class="cell"
          v-bind:style="sellSize"
          v-on:click="checkClick">
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
  data: function () {
    return {
      cellsFound: 0
    }
  },
  computed: {
    sellSize: function() {
      return "width: " + (100 - 1 * this.content.length)/this.content.length + "%;";
    }
  },
  methods: {
    checkClick: function() {
      console.log("click");
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
  margin: 0 0.7% 0.7% 0;
}

.cell:hover {
  box-shadow: 1px 1px 2px #28a745, -1px -1px 2px #28a745; 
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
