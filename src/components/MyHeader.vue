<template>
  <div class="header">
    <nav class="navbar navbar-light bg-dark">
      <div class="container-fluid">
        <img  src="../assets/logo.png" alt=""  class="img-thumbnail">
      </div>
    </nav>
    <select @change="$emit('scelta,')" v-model="genere" class="form-select" aria-label="Default select example">
      <option selected>Genere</option>
      <option value="1">Jazz</option>
      <option value="2">Rock</option>
      <option value="3">Pop</option>
   </select>
  </div>
  
</template>

<script>
export default {
    nome:'MyHeader',
    data(){
      return {
        genere:''
      }
    },
    props:{
      ListaAlbum:Array
    }

}
</script>

<style lang=" scss">
  

</style>