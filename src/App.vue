<template>
  <div class="container">
    <BuscadorCanciones>
    
    </BuscadorCanciones>
   
  </div>



  
  
</template>

<script>
import BuscadorCanciones from './components/BuscadorCanciones.vue'




export default {

  
  name: 'App',
  components: {

    BuscadorCanciones
  }
}
</script>

<style>
  body{
    background-color: black;
  }
  #app {

    background-color: rgb(244, 244, 245); 
   
  }
  .container{
  align-items: center;
   text-align: center;
  }
  
</style>
