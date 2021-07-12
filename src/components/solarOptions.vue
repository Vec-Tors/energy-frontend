<template>
  <div id="main">
    <h1 id="title">Solar Options</h1><br>
    <div id="container">
    <div id="flexItem1">
    <span class="secondBox">You could spend</span><br>
    <span class="dataBox">${{(energy*(pps/3)).toPrecision(6)}}</span><br>
    <span class="secondBox">one time(minus any <a href="https://www.energy.gov/eere/solar/homeowners-guide-federal-tax-credit-solar-photovoltaics">federal or state credits</a>) and buy</span><br>

    <span class="dataBox">{{energy.toPrecision(6)}} {{units}}</span><br>
    <span class="secondBox">worth of solar panels. </span>
    </div>
    <div id="flexItem3">
    </div>
    <div id="flexItem2">
    <span class="secondBox">It would take about</span><br>
    <span class="dataBox">{{((energy*(pps/3))/(ppe*energy*30)).toPrecision(6)}} months</span><br>
    <span class="secondBox">to save enough from your energy bill to save off</span><br>
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
    background-color: rgb(204, 252, 203);
    padding: 10px;
    max-height: 350px;
}
#container{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
} 
#flexItem1{
  padding: 20px ;
  border-style: outset;
  border-width: 2px; 
  border-color: black;
  background-color: rgb(150, 230, 179);
  border-radius: 25px;
}

#flexItem2{
  padding: 20px ;
  border-style: outset;
  border-width: 2px; 
  border-color: black;
  background-color: rgb(150, 230, 179);
  border-radius: 25px;
}

#flexItem3{
  padding: 10px ;
}
#title{
  padding: 10px;
}
.secondBox {
    background: rgb(150, 230, 179);

}
.dataBox{
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-weight: bold;
    font-size: 300%;

}
</style>
