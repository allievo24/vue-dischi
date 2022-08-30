<template>
<div clas="loding">
    <h1>"Loading IN Progress"</h1>
</div>

  
</template>

<script>
export default {
    name:'LodingProgress'
}
</script>

<style lang="scss">
@import '@/style/colori.scss';
.loding{
    position:fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    h1{
      font-size: 10rem;
      color: $backText;
    }
}

</style>