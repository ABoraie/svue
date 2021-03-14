<template>
  <div class="headermenu">
    <a href="#home">Home</a>
    <div class="submenu">
      <button class="submenubtn">Stocks</button>
      <div class="submenucontent">
        <a href="#placeholder">Placeholder</a>
        <a href="#placeholder">Placeholder</a>
      </div>
    </div>
    <div class="submenu">
      <button class="submenubtn" v-on:click="emitToParent(true)">Help</button>
      <div class="submenucontent">
        <a v-for="(testEntry, id) in testData" :key="id" href="#" v-on:click="emitHelpIDToParent(testEntry.id)">
          {{ testEntry.title }}
        </a>
      </div>
    </div>
    <div class="submenu">
      <button class="submenubtn">About</button>
      <div class="submenucontent">
        <a href="#placeholder">placeholder</a>
        <a href="#placeholder">placeholder</a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import axios from "axios";

export default Vue.extend({
  name: "HeaderMenu",
  props: ["visible"],
  data: function() {
    return {
      testData: {}
    };
  },
  mounted() {
    axios.get("help-data.json").then(response => {
      this.testData = response.data.entries; //This is just to get the mock data from the json file
    });
  },
  methods: {
    emitToParent(value: boolean) {
      this.$emit("childToParent", value);
    },
    emitHelpIDToParent(value: number) {
      this.$emit("changeHelpID", value)
    }
  }
});
</script>

<style>
@import "../assets/main.css";
</style>
