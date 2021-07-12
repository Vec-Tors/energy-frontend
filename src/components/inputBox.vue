<template>
  <div id="main">
    <div id=box>
    <div id="container">
     <label for="PCN">Enter how many PC's you have in your room: </label>
      <inputTextField name="PCN" @update="textBoxUpdate" fieldData=""></inputTextField>
      <div class="smalltext">Assumes your PC uses <inputTextField name="PCN" @update="textBoxUpdate" :fieldData="PCP"></inputTextField> watts</div>
    </div>
    <div id="container">
     <label for="PCH"><br>Enter how many hours the PC's are on for: </label>
      <inputTextField name="PCH" @update="textBoxUpdate" fieldData=""></inputTextField>
    </div>
    <div id="container">
      <label for="LBN"><br>Enter the number of lightbulbs in your room: </label>
      <inputTextField name="LBN" @update="textBoxUpdate" fieldData=""></inputTextField>
      <div class="smalltext">Assumes your Lights use <inputTextField name="PCN" @update="textBoxUpdate" :fieldData="LBP"></inputTextField> watts.</div>
    </div>
    <div id="container">
      <label for="LBH"><br>Enter how long these lightbulb's are on for: </label>
      <inputTextField name="LBH" @update="textBoxUpdate" fieldData=""></inputTextField>
    </div>
    <div id="container">
      <label for="ACH"><br>Enter how long the heater/ac is on for (in hours): </label>
      <inputTextField name="ACH" @update="textBoxUpdate" fieldData=""></inputTextField>
      <div class="smalltext">Assumes your heater/ac uses <inputTextField name="PCN" @update="textBoxUpdate" :fieldData="ACP"></inputTextField> watts.</div>
    </div>
    <div id="container">
      <label for="MDN"><br>How many mobile devices are in the room: </label>
      <inputTextField name="MDN" @update="textBoxUpdate" fieldData=""></inputTextField>
      <div class="smalltext">Assumes your mobile devices use <inputTextField name="PCN" @update="textBoxUpdate" :fieldData="MDP"></inputTextField> watts.</div>
    </div>
    <div id="container">
      <label for="MDH"><br>How many hours is each mobile device on for: </label>
      <inputTextField name="MDH" @update="textBoxUpdate" fieldData=""></inputTextField>
    </div>
    </div>
  </div>
</template>

<script>
import inputTextField from "./inputTextField.vue"
export default {
  name: 'inputBox',
  props: {
  
  },
  components:{
    inputTextField
  },
  data: ()=>{
    return{
      PCN:0,
      PCH:0,
      LBN:0,
      MDN:0,
      MDH:0,
      LBH:0,
      ACH:0,
      PCP:400,
      LBP:60,
      ACP:3500,
      MDP:80,
      RIH:4
    }
  },
  methods:{
    textBoxUpdate: function(msg){
      this[msg.name] = msg.content;
       let ret = ((this.LBN * this.LBH * (this.LBP/1000)) + (this.PCN * this.PCH * (this.PCP/1000)) + (this.MDN * this.MDH * (this.MDP/1000)))*this.RIH+ (this.ACH * (this.ACP/1000));
       this.$emit('update',ret)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#main {
  display: flex;
  flex-wrap: wrap;
  background-color: rgb(204, 252, 203);
  padding: 35px 15px;
  border-color: black;
  border-width: 2px;
  flex-direction: column;
  justify-content: flex-end;
}
.smalltext {
font-size: 13px;
font-weight: bold;
}



</style>
