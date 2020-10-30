<template>
  
  <div 
    class="border border-green-700 m-2 p-2 rounded flex justify-between"
    :class="isInjuredClass"
  >
    <div>
      <h3 class="text-lg font-bold">{{ LegumineuseName }} {{ Legumineuse.number }}
      </h3>
      <p>{{ Legumineuse.position }}</p>
    </div>
    
    <base-button
      text="Sélectionner cet ingrédient"
      @click="this.Legumineuse.health === 'out' ? null : addToSelection()"
    >
    </base-button>
  </div>
</template>

<script>
export default {
  name: "Legumineuse-card",
  props: ['Legumineuse'],
  computed: {
    LegumineuseName() {
      if(this.Legumineuse.name.split('.').length > 1){
        return this.Legumineuse.name.split('.')[1]
      }
      return this.Legumineuse.name;
    },
    LegumineuseInjured() {
      if(this.Legumineuse.health == "out"){
        return true
      }
      return false
    },
    isInjuredClass() {
      return { 
        'bg-red-300': this.LegumineuseInjured, 
        'bg-gray-300': !this.LegumineuseInjured 
        }
    },
  },
  methods: {
    addToSelection() {
      this.$emit('add-legumineuse', this.Legumineuse)
    }
  }
}
</script>

<style scoped>

</style>