<template>
  <div>
    <select v-model="genere" id="select-genere" @change="$emit('cambioGenere', genere)">
      <option value="All">All</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Metal">Metal</option>
      <option value="jazz">jazz</option>
    </select> 
  </div>
</template>

<script>
export default {

  name: 'Myselect',
  data () {
    return {
      genere:""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  #select-genere {
    margin-bottom: 50px;
  }
</style>
