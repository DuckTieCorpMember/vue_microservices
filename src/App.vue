<template>
  <div id="app">
    <ActualList/>
  </div>
</template>

<script>
import ActualList from "./components/ActualList"
export default {
  name: 'app',
  components: {
    ActualList
  }
}
</script>

<style>
#app {
  font-family: "Segoe UI", Frutiger, "Frutiger Linotype", "Dejavu Sans", "Helvetica Neue", Arial, sans-serif;
}
</style>
