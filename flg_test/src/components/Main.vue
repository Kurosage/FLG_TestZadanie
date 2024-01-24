<template>
    <div class="main" v-for="card in content" :key="card.id">
        <MainCard class="card" :card="card"></MainCard>
    </div>
</template>
<script>
import MainCard from "./MainCard.vue"
import {ref} from 'vue'
export default{
    name: "main",
    components: {
        MainCard
    },
    setup () {
        const content = ref([
            {
                id:1,
                label:"Первый проект",
                text:"Это моц первый проект, в нем я буду использовать фреймворк Vue. Это проект-прототип интернет магазина техники. Начнем со стандартных разделов страницы сайта.",
                animation:false,
                buttons:false
                
            }, 
            {
                id:2,
                label:"Второй проект",
                text:"Да здравствует анимация",
                animation:true,
                buttons:false
                
            }, 
            {
                id:3,
                label:"Третий проект",
                text:"Нажми на кнопку и узнаешь",
                animation:false,
                buttons:true
                
            }
        ])
        return{content}
        
    }
}
    
</script>



<style scoped>

.main{
    
    display:flex;
    flex-wrap:wrap;
    justify-content: left;
    /* align-items: center; */
    
}
.card{
    
    width: 600px;
    min-width: 300px;
    height: 400px;
    margin: 5px;
    /* background-color: grey; */
    
}
</style>
