<template>
  <div class="album">
    <img :src="details.poster" alt="">
    <h3 class="titleDisc">{{details.title}}</h3>
    <div>{{details.author}}</div>
    <div>{{details.year}}</div>
  </div>
</template>

<script>
export default {
  name: 'Album',
  props: {
    details: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.album {
    width: calc(100% / 5 - 30px);
    margin: 0px 15px 20px 15px;
    background-color: #2e3a46;
    padding: 20px;
    height: 300px;
    color:white;
    text-align: center;
    h3 {
        margin: 10px 0;
    }
    img {
        width: 100%;
    }
    div {
        color: #6e7976;
    }
}

</style>
