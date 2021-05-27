<template>
  <Nav_bar v-bind:showSideMenu="showSideMenu" @updateParentData = "setShow" />
  <HelloWorld msg="Welcome to Your Vue.js App" v-bind:showSideMenu="showSideMenu" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Nav_bar from '../src/components/nav_bar/Nav_bar.vue'
export default {
  name: 'App',
  data(){
    return{
      showSideMenu: false
    }
  },
  components: {
    HelloWorld, Nav_bar
  },
  methods: {
    setShow(value){
      this.showSideMenu = value;
    },
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
  height: 100%;
  margin: 0;
}

html, body{
    margin: 0;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: white;
    width: 100vw;
    overflow-x: hidden;
}
body {
  position: relative;
}

</style>
