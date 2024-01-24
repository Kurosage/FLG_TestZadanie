
<template>
   
    <Head></Head>
    <Main></Main>
    <Footer :activity="activity" class="footer"></Footer>
    
</template>
<script>
import Head from "./components/Head.vue";
import Footer from "./components/Footer.vue";
import Main from "./components/Main.vue";
import axios from "axios";
import {ref} from 'vue';

export default {
    name: "app",
    components: {
        Head,
        Footer,
        Main
    },
    
    onMounted() {
        
    },
    
    setup () {
      const activity = ref([]) // use const because you dont want to lose this value

       

      // Fetch Data Feature
      const fetchActivity = () => {
        return axios.get('https://www.boredapi.com/api/activity')
          .then(response => {
            activity.value= response.data.activity
            
          })
      }
      
   
      return {activity,fetchActivity}
    },
    created () {
      this.fetchActivity()
    }

}
</script>


<style scoped>

.footer{
    background-color:rgb(144, 156, 189);
    color:black;
    width:100%;
    position:fixed;
    right:0;
    bottom:0;
    text-align: center;
    padding-top: 30px;
    padding-bottom: 10px;
    font-size: 25px;
    font-weight: bold;
}
</style>
