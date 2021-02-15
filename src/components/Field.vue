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
    <div class="switch">
      <span class="switch-item square selected"></span>
      <span class="switch-item cross"></span>
      <span class="switch-item question"></span>
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

/* COMMON STYLES */

.cell, span.switch-item {
  border: 3px solid #28a745;
  border-radius: 7px;
}

.is-img, .not-img, .switch-item:hover:not(.selected) {
  background-color: #abe68e;
}

.is-img:hover, .not-img:hover {
  box-shadow: 1px 1px 2px #28a745, -1px -1px 2px #28a745; 
}

.is-img, .not-img, span.cross, span.square, span.question {
  aspect-ratio: 1/1;
}

span.cross, span.square, span.question {
  margin-left: 5%;
  width: 90%;
  background-size: 100% 100%;
}

/*SPECIFIC STYLES*/

.cell {
  margin: 0 0.3% 0.3% 0;
}

.cell:first-child {
  width: 15%!important;
}

.selected {
  background-color: #28a745;
}

.switch {
  width: 15%;
}

span.switch-item {
  width: 28%;
  display: inline-block;
}

span.cross {
  background-image: url("../assets/cross-symbol_icon-icons.com_74149.svg");
}

span.square {
  background-image: url("../assets/lines.svg");
}

span.question {
  background-image: url("../assets/question-mark.svg");
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
  .container-fluid {
    width: 70%;
  }

  .hor {
    aspect-ratio: 1/0.7;
  }
}

@media (min-width: 1440px) {
  .container-fluid {
    width: 55%;
  }
}

@media (min-width: 1920px) {
  .container-fluid {
    width: 50%;
  }
}

</style>
