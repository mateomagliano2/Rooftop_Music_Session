<template>

  <BuscadorCanciones>
    
  </BuscadorCanciones>


  
  
</template>

<script>
import BuscadorCanciones from './components/BuscadorCanciones.vue'

const axios = require('axios');

// Make a request for a user with a given ID
axios.get('https://musicbrainz.org/ws/2/recording?fmt=json&query=under%20the%20bridge')
  .then(function (response) {
    // handle success
    console.log(response);

  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .finally(function () {
    // always executed
  });



export default {

  
  name: 'App',
  components: {

    BuscadorCanciones
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
</style>
