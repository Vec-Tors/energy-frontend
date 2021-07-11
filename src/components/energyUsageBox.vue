<template>
  <div id="main">
      <span id="title"><h1>Energy Usage</h1></span><br>
      <span class="secondBox" id="amountOfenergy">You used about:</span><br>
      <span class="dataBox">{{energy}} {{units}}</span><br>
      <span class="secondBox" id="priceOfenergy">This costs about:</span><br>
      <span class="dataBox">${{energy*ppe}}</span>
  </div>
</template>

<script>
export default {
name:"energyUsageBox",
props:['energy','units','ppe'],
data:()=>{
    return{
        totalPrice:0
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