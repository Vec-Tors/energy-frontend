<template>
  <div id="main">
      <span id="title"><h1>Energy Usage</h1></span><br>
      <span class="secondBox" id="amountOfenergy">You used about:</span><br>
      <span class="dataBox">{{energy}} {{units}}</span><br>
      <span class="secondBox" id="priceOfenergy">This costs about:</span><br>
      <span class="dataBox">${{Math.round(energy*ppe*100)/100}}</span>
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
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    background-color: rgb(204, 252, 203);
}
.secondBox {
    background: white;
}
.dataBox{
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-weight: bold;
    font-size: 300%;
}
</style>
