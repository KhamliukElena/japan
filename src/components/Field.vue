<template>
  <div class="container">
    <div class="container-fluid">
      <div class="row">
        <div class="cell">
          <h2>{{content}}</h2>
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
