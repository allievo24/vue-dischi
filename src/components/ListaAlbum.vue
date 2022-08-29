<template>
    <div class="container">
        <SingolAlbum v-for ="(album, index) in ListaAlbum " :key="index" :album="album"/>

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
        .then(res =>{
            this.ListaAlbum =res.response.data;

        })
        .catch(err =>{
            console.log(err);

        })

        
    },

}
</script>

<style>

</style>