<template>
  <div v-if="visible" class="help-view">
    <div class="helpview-title">
      <h1>
      {{ title }}
      </h1>
    </div>
    <div class="helpview-description">
      {{ description }}
    </div>
    <button v-on:click="emitToParent(false)">Close</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import axios from "axios";
export default Vue.extend({
  name: "HelpView",
  props: ["visible","helpID"],
  data: function() {
    return {
      testData: []
      // visible: true
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
    }
  },
  computed: {
    title: function (): string {
      const t = this.testData.find(x => x['id'] === this.helpID)
      if(t && t['title']){
        return t['title']
      }
      else{
        return "Something went wrong collecting the help information!"
      }
    },
    description: function(): string {
      const obj = this.testData.find(x => x['id'] === this.helpID)
      if(obj && obj['description']){
        return obj['description']
      }
      else{
        return "Could not get the description for this entry."
      }
    }
  }
});
</script>

<style>
@import "../assets/main.css";
</style>
