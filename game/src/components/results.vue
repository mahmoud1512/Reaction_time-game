<template>
  <div class="result">
       Your score is {{score}} ms 
       <p v-if="score<=250">Dragon's reflexes</p>
       <p v-else-if="score<=450"> warrior's reflexes </p>
       <p v-else> turtle's reflexes   </p>
  </div>
</template>

<script>
export default {
     props:['score'],
     mounted()
     {
        console.log(this.score);
     }
     
}
</script>

<style>     
    .result
    {
        margin: 15%;
         color: black;
         font-style: italic;
    }

</style>