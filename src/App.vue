<template>
  <div id="app">
    <Rating :grade="1" :maxItems="5" :hasCounter="true"></Rating>
  </div>
</template>

<script>
import Rating from "./components/Rating.vue";

export default {
  name: "App",
  components: {
    Rating
  }
};
</script>

<style>
#app {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
body {
  height: 100%;
}
</style>
