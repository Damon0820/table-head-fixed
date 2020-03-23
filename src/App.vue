<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <DemoPosAbsolut msg="Welcome to Your Vue.js App"/> -->
		<button v-for="item in list" :key="item.label"  @click="active = item.component">{{item.label}}</button>
    <Component :is="active"></Component>
  </div>
</template>

<script>
import DemoPosAbsolut from './components/demo-pos-absolute.vue'
import DemoPosSticky from './components/demo-pos-sticky.vue'
import DemoStickyTable from './components/demo-stick-table.vue'

export default {
  name: 'app',
  components: {
    DemoPosAbsolut,
		DemoPosSticky,
		DemoStickyTable,
  },
	data() {
		return {
			active: DemoPosSticky,
			list: [
				{
					label: 'DemoPosAbsolut',
					component: DemoPosAbsolut,
				},
				{
					label: 'DemoPosSticky',
					component: DemoPosSticky,
				},
				{
					label: 'DemoStickyTable',
					component: DemoStickyTable,
				},
			]
		}
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
