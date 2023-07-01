<template>

<div class="card" style="width: 18rem;">
  <img src="../assets/fondobuscador.jpg" class="card-img-top" >
  <div class="card-body">
    <h5 class="card-title">Buscador de artistas </h5>
    <input v-model ="info" type="text" class="form-control-sm"  placeholder="Ingresa tu artista o cancion... ">


    <button type="submit" class="btn btn-primary" @click = "buscar">Buscar</button>

    <p class="card-text">{{info}}Encuentra tu artista favorito...crack.</p>


    
  </div>

  <div class="container">

    <p class="comment" v-for = "(valorEncontrados, index) in valorEncontrado" :key="index">
                <strong>{{ valorEncontrados.title}} </strong>  
                <br>

                <strong>{{ valorEncontrados.id}} </strong>  
                <br>
                <strong>{{ valorEncontrados["artist-credit"][0].name}} </strong> 
                <br>
                <strong>{{ valorEncontrados.length/1000}} </strong>  
             
    </p>                  
  </div>
</div>

 

</template>
<script>

const axios = require('axios');





export default {
    name: 'BuscadorCanciones',

    data(){
        return{
            info: "",
            valorEncontrado: null, 

            nombreArtista:""
           
        }
    },
    methods:
    {
        buscar(){
           // this.query = "https://musicbrainz.org/ws/2/recording?fmt=json&query="+ this.info.trim()
         axios.get('https://musicbrainz.org/ws/2/recording?fmt=json&query=under%20the%20bridge')
            .then(response=> {
               console.log(response)

                this.valorEncontrado = response.data.recordings;
               
               


            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .finally(function () {
                // always executed
            });

        }




    }

}



</script>
<style scoped>

</style>