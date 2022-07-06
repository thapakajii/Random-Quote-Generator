<template>
<div class="container mb-4">
  <h1>Color Picker</h1>
  <h2>Choose a color.</h2>
  <button class="play-btn" @click="start">Play</button>
</div>
  <app-color v-if="isPlaying"/>

</template>

<script>
import AppColor from './components/AppColor'
export default {
  name: 'App',
  components: { AppColor 
  },
  data(){
    return{
       isPlaying: false,
    }
  },
  methods: {
    start(){
      this.isPlaying = true
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.play-btn{
  font-size: 1.5rem;
  font-weight: bolder;
  background-color: #52796f;
  color: #fff;
  border: 1px solid transparent;
  border-radius: 5px;
}
</style>
