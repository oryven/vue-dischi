<template>
  <div>
      <header>
            <img alt="Vue logo" src="../assets/logos.png">
      </header>

      <section >

          <div class="container">
              <Album v-for="dicso,i in discList " :key="i" :details="disco"/>
          </div>

      </section>
  </div>
</template>

<script>

import axios from "axios";
import Album from '@/components/Album.vue';

export default {
  name: 'AlbumList',

 components: {
    Album
  },

  data () {
        return {
        apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
        discList: []
    }
  },

  created () {
      this.getAlbumlList ();
  },

  methods () {

    getAlbumlList () {

    axios
    .get (this.apiUrl)
    .then ((result) => {
        this.discList= result.data.response;
        })
    }   
  }
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
    height: 50px;
    background-color: #2e3a46;
    img {
        width: 50px;
    }
}
section {
    background-color: #1e2d3b;
    height: calc(100vh - 50px);
    .container {
        display: flex;
        flex-wrap: wrap;
        width: 70%;
        margin: auto;
        height: 200px;
        background-color: cornflowerblue;
    }
}

</style>
