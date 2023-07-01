<template>

<div class="card" style="width: 18rem;">
  <img src="../assets/fondobuscador.jpg" class="card-img-top" >
  <div class="card-body">
    <h5 class="card-title">Buscador de artistas </h5>
    <input v-model ="info" type="text" class="form-control-sm"  placeholder="Ingresa tu artista o cancion... ">


    <button type="submit" class="btn btn-primary">Buscar</button>

    <p class="card-text">{{info}}Encuentra tu artista favorito...crack.</p>


    
  </div>
</div>

 

</template>
<script>


export default {
    name: 'BuscadorCanciones',

    data(){
        return{
            info: ""
        }
    },


}

</script>
<style scoped>

</style>