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
#main {
    background-color: rgb(204, 252, 203);
}

.inputtextbox{
  border-style: solid;
  border-width: 20px;
  border-color: green;
  background-color: rgb(150, 230, 179);
}
</style>
