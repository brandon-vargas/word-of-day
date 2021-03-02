<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1 v-bind:style="{}">Lesson of the day</h1>
    <WordOfDay/>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import WordOfDay from '@/views/WordOfDay.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld,
    WordOfDay
  }
}
</script>
<style scoped>
.home {
  margin-bottom: 60px;
}
</style>