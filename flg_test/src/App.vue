
<template>
    <Head></Head>
    <Footer></Footer>
    <Main></Main>
    <div>{{ res["data"] }}</div>
</template>
<script>
import Head from "./components/Head.vue"
import Footer from "./components/Footer.vue"
import Main from "./components/Main.vue"
import axios from "axios"
import {ref} from 'vue'
export default{
    
    components:{
        Head,
        Footer,
        Main
    },
    mounted() {
        axios.get('https://www.boredapi.com/api/activity').then(response => (this.res = response));
    },
    methods: {
        
    },
    setup(){
        const res = ref(0)
        return{
            res
        }
    }
    // data() {
    //         return {
    //             res: null
    //         };
    //     },
        
    };
</script>



<style scoped>

</style>
