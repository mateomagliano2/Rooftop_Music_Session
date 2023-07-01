<template>
  <div class="container">
    <BuscadorCanciones>
    
    </BuscadorCanciones>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. 

      Eveniet molestias blanditiis accusamus explicabo aspernatur 
      omnis ullam consectetur fuga alias impedit, eligendi sit id 
      voluptas aliquam. Culpa laborum aliquam totam nobis?
    </p>
  </div>



  
  
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
  background-color: rgb(130, 134, 134);
}
</style>
