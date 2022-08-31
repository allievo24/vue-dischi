<template>
    <div class="container">
        <SingolAlbum v-for ="(album, index) in filtrAlbum " :key="index" :album="album"/>

    </div>
  
</template>

<script>
import axios from 'axios';
import SingolAlbum from './SingolAlbum.vue'

export default {
    name: "ListaAlbum",
    components:{
      SingolAlbum
    },
    props:{
        genereScelto : String
    },
    data(){
        return{
            genere:[],
            ListaAlbum: [],
            endPoint: 'https://flynn.boolean.careers/exercises/api/array/music',
            loadInProgress:true
        };
    },
    computed:{
        filtrAlbum(){
            if(this.genereScelto == ''){
                return this.ListaAlbum;
            }else{
               const listaFiltrata = this.ListaAlbum.filter(album =>{
                   if(album.genre == this.genereSCelto){
                    return true;
                   }else{
                     return false;
                   }
               });
               
                return listaFiltrata;
            }

        }
    },
    created(){
        axios.get(this.endPoint)
        .then(resulta =>{
            this.ListaAlbum = resulta.data.response;
            this.loadInProgress=false
            
            this.ListaAlbum.forEach(album => {
                if(!this.genere.includes(album.genre)){
                    this.genere.push(album.genre)
                }
                
            });
//notifico al padre app vue la lista dei generi
                this.$emit('generiReady',this.genere);

        })
        .catch(err =>{
            console.log(err);
            this.loadInProgress=false
 

        });

        
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