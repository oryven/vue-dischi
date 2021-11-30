<template>
  <div>
    <header>
      <img alt="Vue logo" src="../assets/logot.png">
      <div class="container-select">
        <select v-model="genere" id="select-genere" @change="$emit('cambioGenere', genere)">
          <option value="All">All</option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Metal">Metal</option>
          <option value="Jazz">Jazz</option>
        </select> 
      </div>
        
    </header>
    
  </div>
</template>

<script>
export default {

  name: 'Myheader',

  data () {
    return {
      genere:""
    }
  },

  props: {
      
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
    height: 50px;
    background-color: #2e3a46;
    display: flex;
    align-items: center;
    justify-content: space-between;
    // margin-bottom: 50px;
    img {
        width: 60px;
    }
    .container-select{
      width: 50%;
      text-align: right;
      padding-right: 10px;
    }
}
</style>
