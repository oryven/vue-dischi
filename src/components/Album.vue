<template>
  <div>
      <img :src="dateil.poster" alt="">
      
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

</style>
