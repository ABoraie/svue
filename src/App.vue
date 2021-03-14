<template>
  <div id="app">
    <HeaderMenu v-on:childToParent="onChildClick"  v-on:changeHelpID="changeHelpIDParent" />
    <h1>Welcome to this page</h1>
    <HelpView v-bind:visible="HelpViewFlag" v-bind:helpID="HelpViewEntryID" v-on:childToParent="onChildClick"/>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
// import HelloWorld from "./components/HelloWorld.vue";
import HeaderMenu from "./components/HeaderMenu.vue";
import HelpView from "./components/HelpView.vue";

export default Vue.extend({
  name: "App",
  components: {
    HeaderMenu,
    HelpView
  },
  data: function() {
    return {
      HelpViewFlag: false,
      HelpViewEntryID: 0
    };
  },
  methods: {
    onChildClick(value: boolean) {
      this.HelpViewFlag = value;
    },
    changeHelpIDParent(value: number){
      this.HelpViewFlag = true;
      this.HelpViewEntryID = value;
    }
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
  height: 1000px; /*This shoud be dynamic*/
}
</style>
