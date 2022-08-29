<template>
<div class="card">
    <img :src="album.poster" alt="">
    <h3>{{album.author}}</h3>-->
    <h4>NEW JERSY</h4>
    <span>anno</span>
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

<style>

</style>
