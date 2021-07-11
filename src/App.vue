<template>
  <div id="app">
    <inputBox/>
    <energyUsageBox ppe="10" energy="500" units="btu"/>
  </div>
</template>

<script>
import inputBox from './components/inputBox.vue'
import energyUsageBox from './components/energyUsageBox.vue'

export default {
  name: 'App',
  components: {
    inputBox,
    energyUsageBox
  }
}
</script>

<style scoped>
body{
  background: rgb(243, 243, 243);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display:flex;
  flex-wrap: wrap;
  
}
</style>
