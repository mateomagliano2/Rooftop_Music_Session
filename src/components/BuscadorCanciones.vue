<template>
    <div class="card" style="width: 30rem;">
        <img src="../assets/fondobuscador.jpg" class="card-img-top">
        <div class="card-body">
            <h5 class="card-title">Buscador de artistas </h5>
            <input v-model="info" type="text" class="form-control-sm" placeholder="Ingresa tu artista o cancion... ">


            <button type="submit" class="btn btn-primary" @click="buscar">Buscar</button>

            <p class="card-text">{{ info }}Encuentra tu artista favorito...crack.</p>



        </div>

        <div class="container">
            <table class="table">
                <thead>
                    <tr>
                        <th scope="col">Cancion</th>
                        <th scope="col">Artista</th>
                        <th scope="col">Duracion</th>

                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(valorEncontrados, index) in valorEncontrado" :key="index">
                        <td><strong>{{ valorEncontrados.title }} </strong> </td>
                        <td>
                            <a @click="discografiaArtista(valorEncontrados['artist-credit'][0].artist.id)" href="">{{
                                valorEncontrados["artist-credit"][0].name }}</a>
                        </td>
                        <td><strong>{{ valorEncontrados.length / 1000 }} </strong> </td>
                    </tr>


                </tbody>
            </table>

        </div>


    </div>
</template>
<script>

const axios = require('axios');





export default {
    name: 'BuscadorCanciones',

    data() {
        return {
            info: "",
            valorEncontrado: null,

            nombreArtista: "",
            artistaId: "",

        }
    },
    methods:
    {
        buscar() {
            // this.query = "https://musicbrainz.org/ws/2/recording?fmt=json&query="+ this.info.trim()
            axios.get('https://musicbrainz.org/ws/2/recording?fmt=json&query=under%20the%20bridge')
                .then(response => {
                    console.log(response)

                    this.valorEncontrado = response.data.recordings;
                    this.artistaId



                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
                .finally(function () {
                    // always executed
                });

        },
        discografiaArtista(artistaId) {
            const query = `https://musicbrainz.org/ws/2/release?artist=${artistaId}&fmt=json&type=album`
            axios.get(query)
                .then(response => {
                    console.log(response)
                    console.log(query)




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
.container {
    margin-left: auto;
    margin-right: auto;
}
</style>