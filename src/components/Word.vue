<template>
  <section class='word-container'>
    <h1>umpire</h1>
    <p>a person who impartially decides or resolves a dispute or controversy</p>
    <h2>Synonyms for umpire</h2>
    <Synonym />
    <Synonym />
    <Synonym />
    <Synonym />
    <Synonym />
    <Synonym />
    <h2>Example secntences for umpire</h2>
    <p>usually acts as {it}umpire{/it} in the all-too-frequent squabbles between the two other roommates</p>
  </section>
</template>

<script>
export default {
  name: 'Word',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
