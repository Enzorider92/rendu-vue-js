<template>
  <h1>Ma sélection d'ingrédients</h1>
  
 
 <ul id="example-1">
  <li v-for="(item, index) in selection" :key="index">
    <selectionPlayerCard
    :player="item"
    >


      </selectionPlayerCard>
  </li>
</ul>

</template>

<script>

import selectionPlayerCard from './SelectionPlayerCard.vue'

export default {
  name: "selection-list",
  props: ['selection'],
  components: {
    selectionPlayerCard
  },
  methods: {
  }
}
</script>

<style>

</style>