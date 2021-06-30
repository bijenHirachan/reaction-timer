<template>
  <h1>My reaction timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Results :points = "points" v-if="points"/>
  <Block v-if="isPlaying" :delay="delay" @reaction-time="hideBox"/>
</template>

<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue';

export default {
  name: 'App',
  components: { 
    Block,
    Results
  },
  data(){
    return{
      isPlaying: false,
      delay: null,
      points: null
    }
  },
  methods:{
    start(){
      this.points = null;
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      
    },
    hideBox(result){
      this.isPlaying = false;
      this.points = result;
      console.log(result);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
