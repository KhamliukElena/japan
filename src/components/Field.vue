<template>
  <div class="container">
    <div class="container-fluid">
      <div v-for="row in content.length" :key="row" class="row">
        <div v-for="col in content.length" :key="col" class="cell">
          <h2>Cell {{row.toString() + " " + col.toString() }}</h2>
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
  }
};
</script>

<style scoped>

</style>
