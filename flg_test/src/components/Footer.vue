<template>
  <div >{{ activity }} </div>
</template>
<script>

export default{  
    props:{
        activity:String
    },
    setup(){
        
        
        return{
            
        }
    },
 
    
    

    
    // const activity = ref(props.activity)

   
}


</script>



<style scoped>
div{
    
    color:black;
    /* padding-left:30px; */
    
    font-family:"Oswald", sans-serif;
    font-weight: bold;
    font-size: 25px;
}
</style>
