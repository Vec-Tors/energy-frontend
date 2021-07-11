<template>
  <div id="main">
    <h1 id="title">Solar Options</h1><br>
    <div id="container">
    <div id="flexItem">
    <span class="secondBox">You could spend</span><br>
    <span class="dataBox">${{energy*pps}}</span><br>
    <span class="secondBox">one time(minus any <a href="https://www.energy.gov/eere/solar/homeowners-guide-federal-tax-credit-solar-photovoltaics">federal or state credits</a>) and buy</span><br>
    <span class="dataBox">{{energy}} {{units}}</span><br>
    <span class="secondBox">worth of solar panels. </span>
    </div>

    <div id="flexItem">
    <span class="secondBox">It would take about</span><br>
    <span class="dataBox">{{isNaN(Math.round(energy*pps/(energy*ppe)))?0:Math.round(energy*pps/(energy*ppe))}} months</span><br>
    <span class="secondBox">to save enough from your energy bill to pay off</span><br>
    <span class="dataBox">100%</span><br>
    <span class="secondBox">of the price you paid for solar panels</span>
    </div>
    </div>
  </div>
</template>

<script>
export default {
name:"solarOptions",
props:['energy','units','ppe','pps']
}
</script>

<style scoped>
#main{
    text-align: center;
}
#container{
  display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
  
}
#flexItem{
  padding: 10px ;
}
#title{
  padding: 10px;
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