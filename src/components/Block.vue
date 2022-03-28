<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      CLICK ME
  </div>
</template>

<script>
export default {
    props: ['delay', 'prop'],
    data(){
      return {
        showBlock: false,
        timer: null,
        reactionTime: 0
      
      }
    },
    mounted() {
      setTimeout(() => {
        this.showBlock = true
        this.startTimer()
        console.log(this.delay)
      }, this.delay)
    },
    methods: {
      startTimer(){
        this.timer = setInterval(() => {
          this.reactionTime += 10
        },10)
      },
      stopTimer(){
        clearInterval(this.timer)
        console.log(this.reactionTime)
        this.$emit('end', this.reactionTime)
      }
    }

    
}
</script>

<style>
    .block {
    box-shadow: 0px 0px 10px 4px #4CAF50;
    margin-left: auto;
    margin-right: auto;
    width: 400px;
    height: 25px;
    border-radius: 100px;
    background:  #4CAF50;
    color: white;
    
    padding: 100px 0;
    margin: 40px auto;
    transition-duration: 0.4s;
     display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    font-size: 40px;
  }

  .block:active{
    transform: scale(1.09)
  }

  

@keyframes fadeInOpacity {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}
</style>