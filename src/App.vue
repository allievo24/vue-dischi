<template>
  <div id="app">
    <MyHeader/>
    <ListaAlbum/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import ListaAlbum from './components/ListaAlbum.vue';

export default {
  name: "App",
  components: {
    MyHeader,
    ListaAlbum

  },
};
</script>

<style lang="scss">
  @import "@/style/generali.scss";
   

</style>
