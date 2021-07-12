<template>
  <div id="main">
    <h1 id="title">Historical Data</h1>
    <div v-if='currentSet != "Renewable Only"' id="statesContainer">
        <label for="numberOfStates">How many states' data do you want on the graph: </label>
          <input name="numberOfStates" id="numberOfStates" value="1" @change="updateNumberOfStates" type="number" min="1" max="100">
            <select name="states" v-for="option in numberOfStates" @change="updateGraph" :key="option" class="stateSelect" id="selectStates">
            <option class="stateOption" v-for="state in states" :key="state" :value="state">{{state}}</option>
        </select>
    </div>
    <div id="dataSetContainer">
      <label for="dataSetSelect">Select the data set you want: </label>
      <select id="dataSetSelect" @change="updateDataSet()">
        <option class=dataSetOption v-for="set in dataSets" :key="set" >{{set}}</option>
      </select>
    </div>
    <div id="graphContainer">
      <iframe id="eia_widget" style="width:100%;height:500px" :src="graphURL" load="iframe_load"></iframe>
    </div>
  </div>
</template>

<script>
export default {
name:"graph-box",
data:()=>{
  return{
     states:["AL", "AK", "AZ", "AR", "CA", "CO", "CT", "DC", "DE", "FL", "GA",  "HI", "ID", "IL", "IN", "IA", "KS", "KY", "LA", "ME", "MD", "MA", "MI", "MN", "MS", "MO", "MT", "NE", "NV", "NH", "NJ", "NM", "NY", "NC", "ND", "OH", "OK", "OR", "PA", "RI", "SC","SD", "TN", "TX", "UT", "VT", "VA", "WA", "WV", "WI", "WY"],
    numberOfStates:1,
    dataSets:["All Fuel Types","Petroleum Only","Renewable Only"],
    currentSet:"All Fuel Types",
    graphURL:"",
    graphURLs:[]
  
  }
},
methods:{
  updateNumberOfStates:function(){
let ar = [];
    this.$emit('cons',document.getElementById("numberOfStates").value);
    
    if(document.getElementById("numberOfStates").value<0||Math.round(document.getElementById("numberOfStates").value)!=document.getElementById("numberOfStates").value){
    
      this.numberOfStates=document.getElementById("numberOfStates").value;
    
      document.getElementById("numberOfStates").value = 0;
    
    }else{
    for(var i = 1;i<=document.getElementById("numberOfStates").value;i++){
      ar.push(i);
      }
      this.numberOfStates=ar;
    
    }
    this.updateGraph();
  },
  updateDataSet:function(){
    this.$emit('cons',document.getElementById("dataSetSelect").value)
    this.currentSet = document.getElementById("dataSetSelect").value
    this.updateGraph();
  },
  updateGraph:function(){
    
    if(this.currentSet=='Renewable Only'){
      this.graphURL = "//www.eia.gov/opendata/embed/iframe.php?series_id=TOTAL.RETCBUS.A";
      return;
    }
    const dataSetKeys = ['ELEC.GEN.ALL-','SEDS.PATCB.',"TOTAL.RETCBUS.A"]
    let urlString = []
    let dataSet = dataSetKeys[this.dataSets.indexOf(this.currentSet)];



    let options = document.getElementsByClassName('stateSelect')
    for (let index = 0; index < options.length; index++) {
      const element = options[index].value;
      urlString.push(`${dataSet}${element}${this.currentSet=="All Fuel Types"?"-99.A":".A"}`)
    }
    urlString = urlString.join(';');
    this.graphURL = `//www.eia.gov/opendata/embed/iframe.php?series_id=${urlString}`;
    this.$emit('cons',this.graphURL);
  }
}

}
</script>

<style scoped>
#main {
    background-color: rgb(204, 252, 203);
}
</style>
