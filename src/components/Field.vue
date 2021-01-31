<template>
  <div class="container">
    <div class="container-fluid">
      <div class="row">
        <div class="cell">
          <h2>{{test}}</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Field',
  data: () => ({
    test: "Hello"
  })
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
