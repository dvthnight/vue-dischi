<template>
  <div id="app">
    <HeaderSpotify/>
    <MainSpotify/>
  </div>
</template>

<script>
import HeaderSpotify from "./components/HeaderSpotify.vue"
import MainSpotify from "./components/MainSpotify.vue"

export default {
  name: 'App',
  components: {
    HeaderSpotify,
    MainSpotify,
  }
}
</script>

<style lang="scss">

@import "./assets/scss/common.scss";

#app {
  font-family: "Montserrat", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
</style>
