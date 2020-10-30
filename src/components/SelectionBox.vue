<template>
  <div>Ma sélection : {{ selection.length }}
    <span v-if="nbrIngredients">Ingredients</span>
    <span v-else>Ingredients</span>
  </div>
</template>

<script>
export default {
  name: "selection-box",
  props: ['selection'],
  computed: {
    nbrIngredients() {
      if(this.selection.length > 1){
        return true
      }
      return false
    }
  }
}
</script>

<style>

</style>