<template>
<div id="game">

  <h1 style="padding-top:30px;">Mahmoud'S REACTION TIMER GAME</h1> 

  <p id="motive">keep your concentration high</p>
  <button id="start" @click="start()" :disabled="this.playing" > start game </button>
  <block v-if="this.playing" :del="delay"  @done="endgame" />
  <results   v-if="this.show"  :score="score"/>
</div>



</template>

<script>
import block from './components/block.vue'
import results from './components/results.vue'
export default {
  name: 'App',
  data(){
    return{
      playing:false,
      delay:0,
      score:null,
      show:false

    }
  },

  components:{
    block,
    results
  },
  methods:
  {
    start()
    {
       this.delay=1000+Math.random()*7000
      this.playing=true;
      this.show=false;
     
     // console.log(this.delay);
    },
    endgame(interval)
    {
        this.score=interval;
        console.log(this.score)
        this.playing=false;
        this.show=true;
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
  color: #2c3e50;
 
 
}
#app h1{
   font-size: 2em;
   color: red;

   
}
#title
{
  height: 30px;
  width: 40%;
  border: solid;
  border-radius: 20px;
  margin-left: 30%;
  color: aqua;
  opacity: 70%;
  padding-top: 20px;
  
}

#motive
{
  color: blueviolet;
  font-size: 1.25em;

}

#start{
  height: 40px;
  width: 90px;
  border-radius:20px ;
  background-color: orange;
}


</style>
