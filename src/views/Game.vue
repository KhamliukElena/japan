<template>
  <div class="game">
    <h2>There will be a game</h2>
    <Field/>
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
    //there data should be obtained
    return { "level": 1 };
  },
  methods: {
    //there are methods for game
  }
}
</script>