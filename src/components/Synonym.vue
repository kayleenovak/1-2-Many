<template>
  <section v-on:click='clickSynonym'class='synonym'>
    <h4>{{synonym}}</h4>
  </section>
</template>

<script>

export default {
  name: 'Synonym',
  props: ['synonym'],
  methods: {
    clickSynonym: function(e) {
      const word = e.target.childNodes[0].textContent
      console.log(word)
      this.$emit('updateWord', word)
    }
  }
}

</script>

<style scoped>
  .synonym {
    background-color: #D1F5FF;
    height: 40px;
    border: 4px solid #004E72;
    border-radius: 10px;
    margin: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>