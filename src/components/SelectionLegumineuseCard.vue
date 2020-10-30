<template>
  
  <div 
    class="border border-green-700 m-2 p-2 rounded flex justify-between"
  >

  <p> {{Legumineuse.name }} </p>
  <p> {{Legumineuse.position}} </p>
  <p> {{Legumineuse.birthDate}} </p>
  <img :src="`${loadImg(Legumineuse.image)}`" alt=""/>


  </div>
</template>

<script>

const images = require.context('@/assets/images', false, /\.jpg$|\.jpeg$/)

export default {
  name: "selection-Legumineuse-card",
  props: ['Legumineuse'],
  methods: {
    loadImg(imgPath) {
      return images('./' + imgPath)
    }
}
}
</script>

<style scoped>
  


</style>