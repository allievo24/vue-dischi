<template>
    <div class="Cont_Card">
        <div class="card text-center" style="width: 10rem;" >
            <img class="card-img-top" :src="album.poster" :alt="album.poster"/>
            <h3>{{album.title}}</h3>
            <h4>{{album.author}}</h4>
            <span>{{album.year}}</span>
        </div>
    
    </div>

</template>

<script>
export default {
    nome: 'SingolAlbum',
    props:{
        album:Object
       
    }

}
</script>

<style lang="Scss">
      
      
     
     

</style>
