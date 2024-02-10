<template>
  <div class="block" v-if="this.show" @click="stop()">
    CLICK ME FAST
  </div>
</template>

<script>
export default {
    props: ['del'],
    data(){
        return{
            show:false,
            timer:null,
            interval:0
            
        }
    },
    mounted()
    {
        console.log(this.del)
         setTimeout(()=>{
          this.show=true
           this.start();
         },this.del);
       
    },



    methods:
    {
        start()
        {
             this.timer=setInterval(()=>{this.interval+=10},10)
        },
        stop()
        {
             clearInterval(this.timer);
             console.log(this.interval);
             this.$emit('done',this.interval)  
             this.interval=0; 
              
        }
    }

       
}
</script>

<style>

   .block
   {
        width: 400px;
        border-radius: 20px;
        background-color: #0faf87;
        color:black;
        text-align: center;
        padding: 100px 0;
        margin:40px auto;
   }

</style>