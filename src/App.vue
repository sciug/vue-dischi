<template>
  <div id="app">
    <SiteHeader/>
    <SiteMain/>
    <SiteFooter/>
   
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue";
import SiteMain from "./components/SiteMain.vue";
import SiteFooter from "./components/SiteFooter.vue";


export default {
  name: "App",
  components: {
    SiteHeader,
    SiteMain,
    SiteFooter

  },
};
</script>

<style lang="scss">
@import './assets/scss/variables.scss';
@import '../node_modules/bootstrap/scss/bootstrap.scss';
@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@300;400;500;700&display=swap');
body{
  background-color: $bg_color;
  font-family: 'Rubik', sans-serif;
}

</style>
