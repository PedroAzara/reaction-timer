<template>
  <ul class="github">
  <a href="https://github.com/PedroAzara/reaction-timer">My Github   </a>
  
</ul>
</template>

<script>
export default {

}
</script>

<style>

.github {
    box-shadow: 0px 0px 10px 4px #4078c0;
    margin-left: auto;
    margin-right: auto;
    width: 400px;
    height: px;
    border-radius: 100px;
    background:  #4078c0;
    color: white;
    
    padding: 50px 0;
    margin: 40px auto;
    transition-duration: 0.4s;
    
    justify-content: center;
    align-items: center;
    text-align: center;
    font-size: 40px;
    
  
  }
  a{
    text-decoration: none;
    color: white;
  }

  .github:hover{
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