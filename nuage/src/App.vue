<template>
<div id="app">
<!-- <img class="img-background" src="./assets/photo-1469365556835-3da3db4c253b.jpg" alt=""> -->
  <meteo />

</div>
</template>

<script>


import meteo from './components/meteo.vue'

export default {
  name: 'app',
  components: {
    meteo,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  background-image: url("https://images.unsplash.com/photo-1469365556835-3da3db4c253b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=750&q=80");
  background-repeat: repeat;
  background-attachment: fixed;
  background-size: cover;

}
</style>
