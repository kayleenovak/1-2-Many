<template>
  <section id='search-container'>
    <h1 class='app-name'>1-2-Many</h1>
    <form>
      <input class='search-input' placeholder='Find a synonym for...' />
      <button class='search-btn'>Search</i></button>
    </form>
  </section>
</template>

<script>

export default {
  name: 'Search',
  // created() {
  //   this.$emit('created')
  // }
}

</script>

<style scoped>
  .app-name {
    font-size: 50px;
    margin-bottom: 30px;
    color: white;
  }

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

  .search-btn {
    background-image: linear-gradient(top, #f4f1ee, #fff);
    border-radius: 25px;
    box-shadow: 0px 8px 10px 0px rgba(0, 0, 0, .3), inset 0px 4px 1px 1px white, inset 0px -3px 1px 1px rgba(204,198,197,.5);
    height: 40px;
    margin: 0 30px 30px 0;
    position: relative;
    width: 100px;			
    transition: all .1s linear;
    font-size: 15px;
    margin-top: 15px;
  }

  .search-btn:after{
    color:#e9e6e4;
    content: "";
    display: block;
    font-size: 30px;
    height: 30px;
    text-decoration: none;
    text-shadow: 0px -1px 1px #bdb5b4, 1px 1px 1px white;
    position: absolute;
    width: 60px;
  }

  .search-btn:hover{
    background-image: linear-gradient(top, #fff, #f4f1ee);
    color:#0088cc;
  }
</style>
  