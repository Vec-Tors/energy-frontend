<template>
  <div id="ma">
<topBar />
  <div id="app">
    <inputBox @update="textBoxUpdate" />
    <energyUsageBox :ppe="ppe" :energy="energy" :units="units"/>
    <solarOptions :ppe="ppe" :energy="energy" :units="units" :pps="pps"/>
    <graph-box/>
  </div>
  </div>
</template>

<script>
import inputBox from './components/inputBox.vue'
import energyUsageBox from './components/energyUsageBox.vue'
import solarOptions from './components/solarOptions.vue'
import graphBox from './components/graph-box.vue'
import topBar from './components/topBar.vue'
export default {
  name: 'App',
  components: {
    inputBox,
    energyUsageBox,
    solarOptions,
    graphBox,  
    topBar
  },
  data:()=>{
    return{
    ppe:0.1331,
    energy:0,
    units:"kwh",
    pps:1200
    }
  },
  methods:{
    textBoxUpdate:function(msg){
      this.$emit('cons',this.energy);
      this.energy = msg;
    }
  }


}
</script>

<style>
body {
  background: rgb(188, 255, 245);
 padding: 0px;
 margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: rgb(93, 115, 126);
  display:flex;
  flex-wrap: wrap;
  justify-content: space-around;

}
#main {
  border-style: solid;
  border-width: 2px; 
  border-color: black;
  padding-left: 20px;
  padding-right: 20px;
  margin-top: 15px;
  margin-bottom: 15px;
}
#ma{
  padding: 0px;
}
</style>
