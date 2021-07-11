<template>
  <div id="main">
    <h1 id="title">Historical Data</h1>
    <div id="container">
      <form>
        <label for="numberOfStates">How many states' data do you want on the graph:</label>
          <input name="numberOfStates" id="numberOfStates" value="1" @change="updateNumberOfStates" type="number">
            <select name="states" v-for="option in numberOfStates" :key="option" id="selectStates">
            <option class="stateOption" v-for="state in states" :key="state" :value="state">{{state}}</option>
        </select>
      </form>
    </div>
  </div>
</template>

<script>
export default {
name:"graph-box",
data:()=>{
  return{
     states:["AL", "AK", "AZ", "AR", "CA", "CO", "CT", "DC", "DE", "FL", "GA",  "HI", "ID", "IL", "IN", "IA", "KS", "KY", "LA", "ME", "MD", "MA", "MI", "MN", "MS", "MO", "MT", "NE", "NV", "NH", "NJ", "NM", "NY", "NC", "ND", "OH", "OK", "OR", "PA", "RI", "SC","SD", "TN", "TX", "UT", "VT", "VA", "WA", "WV", "WI", "WY"],
    numberOfStates:1
  
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
  }
}

}
</script>

<style scoped>
#main {
    background-color: rgb(204, 252, 203);
}
</style>
