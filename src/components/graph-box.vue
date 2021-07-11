<template>
  <div id="main">
    <h1 id="title">Historical Data</h1>
    <div id="container">
      <form>
        <select name="states" id="selectStates">
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
     states:["AL", "AK", "AZ", "AR", "CA", "CO", "CT", "DC", "DE", "FL", "GA",  "HI", "ID", "IL", "IN", "IA", "KS", "KY", "LA", "ME", "MD", "MA", "MI", "MN", "MS", "MO", "MT", "NE", "NV", "NH", "NJ", "NM", "NY", "NC", "ND", "OH", "OK", "OR", "PA", "RI", "SC","SD", "TN", "TX", "UT", "VT", "VA", "WA", "WV", "WI", "WY"]

  
  }
}

}
</script>

<style scoped>

</style>