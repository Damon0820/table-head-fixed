<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <DemoPosAbsolut msg="Welcome to Your Vue.js App"/> -->
    <DemoPosSticky msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import DemoPosAbsolut from './components/demo-pos-absolute.vue'
import DemoPosSticky from './components/demo-pos-sticky.vue'

export default {
  name: 'app',
  components: {
    DemoPosAbsolut,
    DemoPosSticky,
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

h1,h2,h3,h4,h5,h6,ul,li, input,textarea,p{margin:0;padding:0;}
li{list-style:none;}
input{outline:none;}
h1,h2,h3,h4,h5,h6{font-style:normal;font-weight:200;font-size: inherit;}
a {color:#666; text-decoration:none}
</style>
