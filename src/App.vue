<template>
  <div id="app">
    <MyHeader @scelta="genere"/>
    <ListaAlbum />
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
      return {
        genere:''
      }
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
