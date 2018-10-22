<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <List/> -->
    <ActualList/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import List from './components/List'
import ActualList from './components/ActualList'
import * as fileF from './assets/json/generated.json'
export default {
  name: 'app',
  components: {
    // HelloWorld
    // List
    ActualList
  },
  data(){
    return{
      file: fileF
    }
  }
}
</script>

<style>
#app {
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
}
</style>
