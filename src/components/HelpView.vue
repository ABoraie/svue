<template>
  <div v-if="visible" class="help-view">
    Here is some help
    <button v-on:click="emitToParent(false)">Close</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "HelpView",
  props: ["visible"],
  data: function() {
    return {
      helpID: null,
      title: null,
      description: null
      // visible: true
    };
  },
  methods: {
    emitToParent(value: boolean) {
      this.$emit("childToParent", value);
    }
  }
});
</script>

<style>
@import "../assets/main.css";
.help-view {
  width: 90%;
  height: 90%;
  background-color: blue;
  margin: 0px auto;
}
</style>
