
<template>
    <div class="body">
        <Head class="head"></Head>
        <Main class="main"></Main>
        <Footer :activity="activity" class="footer"></Footer>
    </div>
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
.body{
    width: 100%;
    height: 100vh;
    display: flex;
    background-color: #c2cdec;
    flex-direction: column;
}

.head,
.footer {
    height: 30px;
    
}
.footer{
    position: fixed;
    bottom: 0;
    
    text-align: center;
    padding: 0 0 15px 15px;
    background-color: rgb(86, 143, 182);
    width: 100%;
}

</style>
