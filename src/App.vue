<template>
  <div>
    
    <ex03-page v-show="true"></ex03-page>
  </div>
</template>

<script>

import Ex03Page from "./components/ex03/Ex03Page.vue";

export default {
  name: "app",
  components: {
    
    Ex03Page
  }
};
</script>

<style>
</style>