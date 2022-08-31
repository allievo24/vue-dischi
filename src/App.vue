<template>
  <div id="app">
    <MyHeader :ListaGeneri="ListaGeneri" @cambiaGenere="ricerca" />
    <ListaAlbum @generiReady="getListaGeneri" :genereScelto="genereScelto"/>
  </div>
</template>

<script>
import MyHeader from "./components/MyHeader.vue";
import ListaAlbum from "./components/ListaAlbum.vue";

export default {
  name: "App",
  components: {
    MyHeader,
    ListaAlbum,
  },
  data(){
    return{
      ListaGeneri:[],
      genereSclto : ''
    }
  },

  methods:{
    getListaGeneri(allgeneri){
        this.ListaGeneri = allgeneri;
    },
    ricerca(ricercaGenere){
      this.genereScelto = ricercaGenere

    },




  }
};
</script>

<style lang="scss">
@import "@/style/generali.scss";
.navbar {
  height: 100px;
  .container-fluid {
        height: 100%;
    img {
      height: 100%;
    }
  }
}
</style>
