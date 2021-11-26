<template>
  <div id="app">
    
    <AlbumList/>
  </div>
  
</template>

<script>
import AlbumList from './components/AlbumList.vue'

export default {
  name: 'App',
  components: {
    AlbumList
  }
}

</script>




<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
