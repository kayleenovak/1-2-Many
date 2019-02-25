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
    Word,
    Search
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
  display: grid;
  grid-template-columns: 400px 1fr;
  height: 100%;
}

html {
  height: 100%;
  padding: none;
  margin: 0;
}

body {
  height: 100%;
  margin: 0;
}
</style>
