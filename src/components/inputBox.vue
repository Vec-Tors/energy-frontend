<template>
  <div class="main">
    <div id="box">
      <inputTextField @update="textBoxUpdate" fieldData="test"></inputTextField>
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
      fieldData:''
    }
  },
  methods:{
    textBoxUpdate: function(msg){
      this.$emit('update',msg)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main {
  display: flex;
  flex-wrap: wrap;
}
#box {
background: rgb(243, 243, 243);
}


</style>
