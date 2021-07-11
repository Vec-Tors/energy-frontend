<template>
       <span><span type='text' class="inputtextbox" @keyup="onChange()" contenteditable>{{fieldData}}</span></span>

  
</template>

<script>
export default {
    name:'inputTextField',
    props:["fieldData"],
    data:()=>{
        return{
            fieldContent:''
        }
    },
    methods:{
      onChange:function (){
        this.fieldContent = document.getElementsByClassName("inputtextbox")[0].innerText;
        console.log(this.fieldContent)
        this.$emit('update',this.fieldContent)
      }
    }
    
}
</script>

<style scoped>
.inputtextbox{
  border-style: solid;
  border-width: 20px;
  border-color: green;
}
</style>