<template>
  <div id="app">
    <HeaderMenu />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
// import HelloWorld from "./components/HelloWorld.vue";
import HeaderMenu from "./components/HeaderMenu.vue";

export default Vue.extend({
  name: "App",
  components: {
    HeaderMenu
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
</style>
