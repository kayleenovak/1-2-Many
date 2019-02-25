<template>
  <section class='word-container'>
    <h1 class='word-name'>umpire</h1>
    <p class='word-definition'>a person who impartially decides or resolves a dispute or controversy</p>
    <h2 class='synonyms-heading'>Synonyms for umpire</h2>
    <h2 class='example-heading'>Example secntences for umpire</h2>
    <p class='example-sentence'>usually acts as {it}umpire{/it} in the all-too-frequent squabbles between the two other roommates</p>
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
  .word-container {
    text-align: left;
    margin-left: 40px;
  }

  .word-name {
    font-size: 40px;
    font-weight: bold;
    margin-bottom: 7px;
  }

  .word-definition {
    margin-top: 0;
    color: gray;
  }

  
</style>
