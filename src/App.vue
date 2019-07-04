<template>
  <div id="app">
      <section>
     <h1>20:19</h1>
      <p>26th May 2021</p>
      <Notifications v-bind:info="this.allNotifs" />
      </section>
  </div>
</template>

<script>
import Notifications from "./components/Notifs.vue"
import axios from "axios"

export default {
  name: 'app',
  data(){
        return {
            notifList: "https://api.myjson.com/bins/19wyhe",
            allNotifs: [],

        }
    },
    mounted() {
        axios.get(this.notifList)
        .then ( res => {

          this.allNotifs = res.data.sort(function(a, b){
            return b.timestamp - a.timestamp;
          })
  
        })
    console.log(this.allNotifs);
    
    },
    methods: {
      
    },
  components: {
    Notifications
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
body {
            margin: 0;
            padding: 0;
            
        }
        section {
            width: 600px;
            min-height: 1000px;
            margin: 0 auto;
            background-image: url("https://cdn.pixabay.com/photo/2016/02/19/11/00/palm-tree-1209536_960_720.jpg"); 
            background-size: cover;
            text-align: center;
        }
        h1 {
            display: inline-block;
            font-size: 120px;
            font-weight: bold;
            margin: 0;
            color: white;
        }
        p {
            font-size: 25px;
            font-weight: bold;
            margin-top: 0;
            
        }
        
</style>
