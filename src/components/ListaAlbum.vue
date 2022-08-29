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
        .then(resulta =>{
            this.ListaAlbum = resulta.data.response;

        })
        .catch(err =>{
            console.log(err);

        })

        
    },

}
</script>

<style lang="scss">
  @import "@/style/generali.scss";
       
     .container{
        display: flex;
        flex-wrap: wrap;
        border: solid 2px blue;
      
      
        
     }
       .Cont_Card{
        width: calc(100% / 5 );
        margin: auto;
        
       
      }
      
</style>