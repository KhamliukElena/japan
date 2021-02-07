<template>
    <div class="container-fluid">
      <div v-for="row in content.length + 1" :key="row" class="row">
        <div v-for="col in content.length + 1" :key="col"
        v-bind:style="sellSize"
        v-on:click="checkClick"
        v-bind:class="getImg(row-1, col-1)"
        class="cell not-set d-flex align-items-center">
        <span></span>
        <p v-if="row == 1 || col == 1" v-html="fillTask(row-1, col-1)"
        class="font-weight-bold"></p>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Field',
  props: {
    content: {
      type: Array,
      required: true
    },
    cellsToFind: {
      type: Number,
      required: true
    }
  },
  data: function () {
    return {
      cellsFound: 0,
    }
  },
  computed: {
    sellSize: function() {
      return "width: " + (85 - 0.3 * (this.content.length + 1)) / this.content.length + "%;";
    },
    console: () => console
  },
  methods: {
    checkClick: function(e) {
      let currentCell = e.target;
      if (currentCell.classList.contains('description')) {
        return; //do nothing if a cell is descriptional, not for playing
      }
      else if (currentCell.classList.contains('not-img')) {
        var child = currentCell.children[0];
        child.classList.add("cross");
      }
      else {
        var child = currentCell.children[0];
        child.classList.add("square");
        this.cellsFound++;
        if (this.cellsToFind === this.cellsFound) {
          console.log("victory");
        }
      }
    },
    getImg: function (i, j) {
      if (i == 0) {
        return "description hor";
      }
      else if (j == 0) {
        return "description vert";
      }
      else if (this.content[i-1][j-1] == 1) {
        return "is-img";
      }
      else {
        return "not-img";
      }
    },
    fillTask: function(i, j) {
      let inner = "";
      let num = 0;
      if (i == 0) {
        if (j == 0) return;
        for (i; i<this.content.length; i++) {
          if (this.content[i][j-1] == 1) {
            num++;
          }
          else if (num != 0) {
            inner += num.toString() + "<br>";
            num = 0;
          }
        }
      }
      else if (j == 0) {
        for (j; j<this.content.length; j++) {
          if (this.content[i-1][j] == 1) {
            num++;
          }
          else if (num != 0) {
            inner += num.toString() + " ";
            num = 0;
          }
        }
      }
      if (num != 0) inner += num.toString();
      if (inner == "") inner+="0";
      return inner;
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

.cell:first-child {
  width: 15%!important;
}

span.cross, span.square {
  display: inline-block;
  margin-left: 5%;
  width: 90%;
  aspect-ratio: 1/1;
  background-size: 100% 100%;
}

span.cross {
  background-image: url("../assets/cross-symbol_icon-icons.com_74149.svg");
}

span.square {
  background-image: url("../assets/lines.svg");
}

.is-img, .not-img {
  background: #abe68e;
  aspect-ratio: 1/1;
}

.is-img:hover, .not-img:hover {
  box-shadow: 1px 1px 2px #28a745, -1px -1px 2px #28a745; 
}

.hor {
  height: auto;
}

.hor:first-child {
  border: none;
}

p {
  margin: 0 auto;
}

@media (min-width: 992px) {
  .hor {
    aspect-ratio: 1/0.9;
  }
}

</style>
