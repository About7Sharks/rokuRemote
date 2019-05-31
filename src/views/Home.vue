<template>
  <div class="remote">
    <div id="row1">
      <b-row align-h="center">
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
    </div> 
  </div>
</template>
<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'home',
  components: {
    // HelloWorld
  },
  methods:{
    togglePlayPause(){
      axios.post('http://192.168.0.2:8060/keypress/play')
    },
    up(){
      axios.post('http://192.168.0.2:8060/keypress/up')
    },
    left(){
      axios.post('http://192.168.0.2:8060/keypress/left')
    },
    right(){
      axios.post('http://192.168.0.2:8060/keypress/right')
    },
    down(){
      axios.post('http://192.168.0.2:8060/keypress/down')
    },
    home(){
      axios.post('http://192.168.0.2:8060/keypress/home')
    },
    ok(){
      axios.post('http://192.168.0.2:8060/keypress/select')
    },
    volumeUp(){
      axios.post('http://192.168.0.2:8060/keypress/VolumeUp')
    },
    volumeDown(){
      axios.post('http://192.168.0.2:8060/keypress/VolumeDown')
    }
  
  }
}
</script>
