<template>
  <div id="app">
    <slider />
  </div>
</template>

<script>
import slider from "./components/slider.vue";

export default {
  name: "App",
  components: {
    slider
  }
};
</script>

<style>
* {
  font-family: system-ui;
}
</style>
