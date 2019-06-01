<template>
  <div class="remote">
   <b-row align-h='center'>
      <h3>IP:</h3> <input type="number" v-model="ip">
    </b-row>
    <div id="row1">
      <b-row align-h="center">
        <b-button variant="outline-info" @click="back()">Back</b-button>
      <b-button variant="outline-info"  @click="home()">Home</b-button>
      </b-row>
      <b-row align-h="center">
      <b-button variant="outline-info" @click="volumeUp()">Volume Up</b-button>
      <b-button variant="outline-info" @click="volumeDown()">Volume Down</b-button>
      </b-row>
      <b-row align-h="center">
      <b-button variant="outline-info" @click="togglePlayPause()">Play</b-button>
      <b-button variant="outline-info" @click="togglePlayPause()">Pause</b-button>
      </b-row>
      <br>
      <b-row align-h="center">
      <b-button variant="outline-info" @click="up()">Up</b-button>
      </b-row>
      <b-row align-h="center">
      <b-button variant="outline-info" @click="left()">Left</b-button>
      <b-button variant="outline-info" @click="ok()">Ok</b-button>
      <b-button variant="outline-info" @click="right()">Right</b-button>
      </b-row>
      <b-row align-h="center">
      <b-button variant="outline-info" @click="down()">Down</b-button>
      </b-row>
      <b-row align-h="center">
        <b-button variant="danger" @click="netflix()">Netflix</b-button>
                <b-button @click="getApps()">Apps</b-button>

      </b-row>
    </div> 
  </div>
</template>
<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'home',
  data(){
    return{
      ip:17
    }
  },
  components: {
    // HelloWorld
  },
  methods:{
 getApps(){
      axios.get('http://192.168.0.'+this.ip+':8060/query/apps').then((res)=>{
        console.log(res)
      })
     
    },
    netflix(){
      axios.post('http://192.168.0.'+this.ip+':8060/launch/12')
    },
    back(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/back')
    },
    togglePlayPause(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/play')
    },
    up(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/up')
    },
    left(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/left')
    },
    right(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/right')
    },
    down(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/down')
    },
    home(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/home')
    },
    ok(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/select')
    },
    volumeUp(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/VolumeUp')
    },
    volumeDown(){
      axios.post('http://192.168.0.'+this.ip+':8060/keypress/VolumeDown')
    }
  
  }
}
</script>
<style>
button{
  width: 33vw;
  height: 10vh;
}
</style>
