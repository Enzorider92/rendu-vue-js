<template>
  <h1>Liste des ingrédients {{ LegumineusesData.name }} </h1>

  <selection-box 
    :selection="selection"
  >
  </selection-box>

  <Legumineuse-card
    v-for="(Legumineuse, index) in LegumineusesData.Legumineuses"
    :key="index"
    :Legumineuse="Legumineuse"
    @add-Legumineuse="addLegumineuseToSelection"
    >
  </Legumineuse-card>
</template>

<script>
import LegumineusesData from '../assets/data/Legumineuses.json'
import LegumineuseCard from './LegumineuseCard.vue'
import SelectionBox from './SelectionBox.vue'

export default {
  name: "Legumineuse-List",
  components: {
    LegumineuseCard,
    SelectionBox
  },
  data() {
    return {
      LegumineusesData : LegumineusesData,
      selection: []
    }
  },
  methods: {
    addLegumineuseToSelection(Legumineuse) {
      this.selection.push(Legumineuse)
      this.$emit('update-selection', Legumineuse)
    }
  }
}
</script>

<style>

</style>