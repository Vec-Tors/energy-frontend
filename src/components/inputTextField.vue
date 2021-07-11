<template>
       <span><input type='text' class="inputtextbox" v-on:onchange="console.log(this.value)" :value="fieldData"></span>

  
</template>

<script>
export default {
    name:'inputTextField',
    props:["fieldData"],
    data:()=>{
        return{
            
        }
    }
    
}
</script>

<style scoped>
#inputtextbox{
  border-style: solid;
  border-width: 20px;
  border-color: green;
}
</style>