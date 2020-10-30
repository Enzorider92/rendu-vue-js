<template>
  <nav-bar
    @change-component="updateSelectedComponent"
  ></nav-bar>

  <keep-alive>
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @update-selection="updateSelection"
    >
    </component>
  </keep-alive>
  
</template>

<script>
import LegumineuseList from './components/LegumineuseList.vue'
import SelectionList from './components/SelectionList.vue'

import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    LegumineuseList,
    NavBar,
    SelectionList
  },
  data() {
    return {
      selectedComponent: 'Legumineuse-list',
      selectionArray: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "selection-list") {
        return { selection: this.selectionArray }
      }
      return false
    }
  },
  methods: {
    updateSelectedComponent(comp) {
      this.selectedComponent = comp
    },
    updateSelection(Legumineuse) {
      this.selectionArray.push(Legumineuse)
    }
  }
}
</script>
<style>

</style>
