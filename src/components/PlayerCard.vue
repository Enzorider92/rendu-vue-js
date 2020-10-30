<template>
  
  <div 
    class="border border-green-700 m-2 p-2 rounded flex justify-between"
    :class="isInjuredClass"
  >
    <div>
      <h3 class="text-lg font-bold">{{ playerName }} {{ player.number }}
      </h3>
      <p>{{ player.position }}</p>
    </div>
    
    <base-button
      text="Sélectionner cet ingrédient"
      @click="addToSelection"
    >
    </base-button>
  </div>
</template>

<script>
export default {
  name: "player-card",
  props: ['player'],
  computed: {
    playerName() {
      if(this.player.name.split('.').length > 1){
        return this.player.name.split('.')[1]
      }
      return this.player.name;
    },
    playerInjured() {
      if(this.player.health == "out"){
        return true
      }
      return false
    },
    isInjuredClass() {
      return { 
        'bg-red-300': this.playerInjured, 
        'bg-gray-300': !this.playerInjured 
        }
    },
  },
  methods: {
    addToSelection() {
      this.$emit('add-player', this.player)
    }
  }
}
</script>

<style scoped>

</style>