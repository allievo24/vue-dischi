<template>
    <div class="container">
        <SingolAlbum v-for ="(album, index) in ListaAlbum " :key="index" :album="ListaAlbum"/>

    </div>
  
</template>

<script>
import axios from 'axios';
import SingolAlbum from './SingolAlbum.vue'

export default {
    name: 'ListaAlbum',
    components:{
      SingolAlbum
    },
    data(){
        return{
            ListaAlbum: [],
            endPoint: 'https://flynn.boolean.careers/exercises/api/array/music'
        }
    },
    created(){
        axios.get(this.endPoint)
        .then(response =>{
            this.ListaAlbum =response.data;

        })
        .catch(err =>{
            console.log(err);

        })

        
    },

}
</script>

<style>

</style>