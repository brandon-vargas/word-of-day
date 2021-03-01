<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
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
