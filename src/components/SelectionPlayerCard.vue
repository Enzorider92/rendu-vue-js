<template>
  
  <div 
    class="border border-green-700 m-2 p-2 rounded flex justify-between"
  >

  <p> {{player.name }} </p>
  <p> {{player.position}} </p>
  <p> {{player.birthDate}} </p>
  <img :src="`${loadImg(player.image)}`" alt=""/>


  </div>
</template>

<script>

const images = require.context('@/assets/images', false, /\.jpg$|\.jpeg$/)

export default {
  name: "selection-player-card",
  props: ['player'],
  methods: {
    loadImg(imgPath) {
      return images('./' + imgPath)
    }
}
}
</script>

<style scoped>
  


</style>