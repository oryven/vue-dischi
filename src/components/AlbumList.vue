<template>
  <div>
      <section >
          <div class="container">
              <Album v-for="disco,i in filtraGeneri" :key="i" :details="disco"/>
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
        discList: [],
    }
  },

  props: {
      selectedOption: String
  },

  created () {
    this.getAlbumList();
  },
  computed: {
    filtraGeneri(){
      if (this.genereSelezionato === '' || this.genereSelezionato === "All"){
        return this.discList;
      }
        return this.discList.filter((item) => {
        return item.genre.includes(this.genereSelezionato);
      });
    }
  },

  methods: {
  
    getAlbumList() {
        axios
        .get (this.apiUrl)
        .then ((result) => {
            this.discList = result.data.response;
        })
    },
   
    // cerca(termine){
    //   console.log(termine);
    //   if ( this.termine === "all"){
    //     return this.discList
    //   }
    //   return this.discList.filter((item) => {
    //     return item.genre.includes(this.termine)
    //   })
    // } 
  } 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

section {
    background-color: #1e2d3b;
    
    // height: calc(100vh - 50px);
    // overflow-y: scroll;
    text-align: center;
    .container {
        display: flex;
        flex-wrap: wrap;
        width: 70%;
        margin: auto;
    }
}

</style>
