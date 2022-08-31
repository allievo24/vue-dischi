<template>
  <div class="header">
    <nav class="navbar navbar-light bg-dark">
      <div class="container-fluid">
        <img  src="../assets/logo.png" alt=""  class="img-thumbnail">
      </div>
    </nav>
    <select @chenge="$emit('cambiaGenere' , genereSelezionato)" v-model="genereSelezionato" class="form-select" aria-label="Default select example">
      <option selected>Genere</option>
      <option v-for="(genere, index ) in ListaGeneri" :key="index" :value="genere">{{genere}}</option>
      
   </select>
  </div>
  
</template>

<script>
export default {
    nome:'MyHeader',
    
    props:{
      ListaGeneri:Array
    },
    data(){
      return{
        genereSelezionato :''
      }
    }

}
</script>

<style lang=" scss">
  

</style>