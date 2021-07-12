<template>
  <div id="main">
      <span id="title"><h1>Energy Usage<br><span id="secondBox">per day</span></h1></span>
      <span class="secondBox" id="amountOfenergy">You used about:</span><br>
      <span class="dataBox">{{energy.toPrecision(5)}} {{units}}</span><br>
      <span class="secondBox" id="priceOfenergy">This costs about:</span><br>
      <span class="dataBox">${{(energy*ppe).toPrecision(5)}}</span>
  </div>
</template>

<script>
export default {
name:"energyUsageBox",
props:{energy:Number,units:String,ppe:Number},
data:()=>{
    return{
    }
}
}
</script>

<style scoped>
#main{
    text-align: center;
    padding: 10px;
    padding-bottom: 0px;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    background-color: rgb(204, 252, 203);
}
#title{
    margin: 0px 0px 0px 0px;
}
#secondBox{
    font-size: 15px;
    font-weight: normal;
}
.dataBox{
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-weight: bold;
    font-size: 300%;
}
</style>
