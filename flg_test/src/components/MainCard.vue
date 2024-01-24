<template>
  <div class="container">
    <label>{{ card.text }}</label>
    <hr>
    <div class="content"></div>
  </div>
</template>
<script>
export default{
    name: "maincard",
    props:{
        card:Object
    },
    emits:{
        
    },
    setup () {
        
        
    },
    
}
</script>



<style scoped>
/* .container{
    display: flex;
    flex-direction: column;
} */
</style>
