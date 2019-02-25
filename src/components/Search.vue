<template>
  <section id='search-container'>
    <h1>1-2-Many</h1>
    <form>
      <input class='search-input' placeholder='Find a synonym for...' />
      <button class='search-btn'>Search</button>
    </form>
  </section>
</template>

<script>

export default {
  name: 'Search'
}

</script>

<style scoped>
  #search-container {
    background: #004E72;
  }

  .search-input {
    width: 80%;
    min-width: 200px;
    height: 40px;
    border-radius: 10px;
    border: none;
    padding: 0 0 0 10px;
    font-size: 20px;
    background-image: linear-gradient(to bottom, rgba(255,252,252,1) 0%,rgba(229,235,238,1) 81%,rgba(215,222,227,1) 100%,rgba(245,247,249,1) 100%,rgba(215,222,227,1) 101%);
  }

  .search-input::placeholder {
    font-size: 20px;
  }
</style>
  