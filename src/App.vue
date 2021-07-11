<template>
  <div id="app">
    <inputBox/>
    <energyUsageBox ppe="10" energy="500" units="btu"/>
    <solarOptions ppe="10" energy="500" units="btu" pps="40"/>
    <graph-box/>
  </div>
</template>

<script>
import inputBox from './components/inputBox.vue'
import energyUsageBox from './components/energyUsageBox.vue'
import solarOptions from './components/solarOptions.vue'
import graphBox from './components/graph-box.vue'
export default {
  name: 'App',
  components: {
    inputBox,
    energyUsageBox,
    solarOptions,
    graphBox
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
  justify-content: space-around;
  
}
</style>
