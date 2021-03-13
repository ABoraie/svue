<template>
    <div class="headermenu">
        <!-- {{ msg }} -->
        <a href="#home">Home</a>
        <div class="submenu">
            <button class="submenubtn">Stocks</button>
            <div class="submenucontent">
                <a href="#placeholder">Placeholder</a>
                <a href="#placeholder">Placeholder</a>
            </div>
        </div>
        <div class="submenu">
            <button class="submenubtn">About</button>
            <div class="submenucontent">
                <a href="#placeholder">placeholder</a>
                <a href="#placeholder">placeholder</a>
            </div>
        </div>
        <div class="submenu">
            <button class="submenubtn">Contribute</button>
            <div class="submenucontent">
                <a href="#placeholder">placeholder</a>
                <a href="#placeholder">placeholder</a>
            </div>
        </div>
        
    </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "HeaderMenu",
  data: function () {
      return {
          msg: "hej"
      }
  },
  created: function() {
    console.log("HEj")
  }
});
</script>

<style>
@import "../assets/main.css";
</style>