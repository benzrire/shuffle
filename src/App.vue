<template>
  <div id="app">
    <Carousel />
    <Navbar />
  </div>
</template>

<script>
import Carousel from "./components/Carousel.vue";
import Navbar from "./components/Navbar.vue";

export default {
  name: "App",
  components: {
    Carousel,
    Navbar
  }
}
</script>

<style>
#app {
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  /*temp*/
  margin-bottom: 500px;
}
</style>
