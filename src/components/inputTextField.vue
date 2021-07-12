<template>
       <span><span type='text' :id="name" @keyup="onChange()" contenteditable>{{fieldData}}</span></span>

  
</template>

<script>
export default {
    name:'inputTextField',
    props:["fieldData","name"],
    data:()=>{
        return{
            fieldContent:''
        }
    },
    methods:{
      onChange:function (){
        this.fieldContent = document.getElementById(this.name).innerText;
        console.log(this.fieldContent)
        this.$emit('cons',this.fieldContent)
        this.$emit('update',{content:this.fieldContent,name:this.name})
      }
    }
    
}
</script>

<style scoped>
span span{
  padding: 0px 20px;
   border-style: dotted;
  border-width: 1px;
  border-color: black;
    margin: 7px;

}
span span:hover{
 border-style: outset;
 border-width: 2px;
  border-color: black;


}
</style>
