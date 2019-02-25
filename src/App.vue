<template>
  <div id="app">
    <Search />
    <Word />
  </div>
</template>

<script>
import Search from './components/Search.vue'
import Word from './components/Word.vue'

export default {
  name: 'app',
  components: {
    Word
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
