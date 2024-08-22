<script>
import AppMain from './components/AppMain.vue';
import MainFooter from './components/MainFooter.vue';
import MainHeader from './components/MainHeader.vue';

  export default {
    name: "",
    components:{
      MainHeader,
      AppMain,
      MainFooter
    }
  }
</script>

<template>
  <MainHeader/>
  <AppMain/>
  <MainFooter/>
</template>

<style lang="scss">
  @use "../styles/general.scss";
</style>
