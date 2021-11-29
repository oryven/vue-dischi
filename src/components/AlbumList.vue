<template>
  <div>
      <header>
            <img alt="Vue logo" src="../assets/logot.png">
      </header>
      
      <section >
          <Myselect/>
          <div class="container">
              <Album v-for="disco,i in discList" :key="i" :details="disco"/>
          </div>

      </section>
  </div>
</template>

<script>
import axios from "axios";
import Album from '@/components/Album.vue';
import Myselect from '@/components/Myselect.vue';

export default {
  name: 'AlbumList',
  components: {
    Album,
    Myselect
  },
  data () {
    return {
        apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
        discList: []
    }
  },
  created () {
    this.getAlbumList();
  },
  methods: {
    getAlbumList() {
        axios
        .get (this.apiUrl)
        .then ((result) => {
            this.discList = result.data.response;
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
    display: flex;
    align-items: center;
    img {
        width: 60px;
    }
}
section {
    background-color: #1e2d3b;
    height: calc(100vh - 50px);
    padding-top: 50px ;
    overflow-y: scroll;
    text-align: center;
    .container {
        display: flex;
        flex-wrap: wrap;
        width: 70%;
        margin: auto;
    }
}

</style>
