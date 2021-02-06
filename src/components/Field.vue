<template>
  <div class="container">
    <div class="container-fluid">
      <div v-for="row in content.length + 1" :key="row-1" class="row">
        <div v-for="col in content.length + 1" :key="col-1" class="cell not-set"
          v-bind:style="sellSize"
          v-on:click="checkClick"
          v-bind:class="getImg(row-1, col-1)">
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
      return "width: " + (100 - 1 * (this.content.length + 1))/(this.content.length + 1) + "%;";
    },
    console: () => console
  },
  methods: {
    checkClick: function() {
      console.log("click");
    },
    getImg: function (i, j) {
      if (i == 0) {
        return "description hor";
      }
      else if (j == 0) {
        return "description";
      }
      else if (this.content[i-1][j-1] == 1) {
        return "is-img";
      }
      else {
        return "not-img";
      }
    }
  }
};
</script>

<style lang="scss" scoped>

.container {
  width: 100%;
}

.cell {
  border: 3px solid #28a745;
  border-radius: 7px;
  margin: 0 0.3% 0.3% 0;
}

.is-img, .not-img {
  background: #abe68e;
  aspect-ratio: 1/1;
}

.hor {
  aspect-ratio: 1/1.25;
}

.cell:hover {
  box-shadow: 1px 1px 2px #28a745, -1px -1px 2px #28a745; 
}

.hor:first-child {
  border: none;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
