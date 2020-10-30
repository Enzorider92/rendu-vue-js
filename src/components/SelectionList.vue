<template>
  <h1>Ma sélection d'ingrédients</h1>
  
 
 <ul id="example-1">
  <li v-for="(item, index) in selection" :key="index">
    <selectionLegumineuseCard
    :Legumineuse="item"
    >


      </selectionLegumineuseCard>
  </li>
</ul>

</template>

<script>

import selectionLegumineuseCard from './SelectionLegumineuseCard.vue'

export default {
  name: "selection-list",
  props: ['selection'],
  components: {
    selectionLegumineuseCard
  },
  methods: {
  }
}
</script>

<style>

</style>