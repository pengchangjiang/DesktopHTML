<template>
  <div id="app">
    <MainMap/>
  </div>
</template>

<script>
import MainMap from "./components/MainMap.vue";

export default {
  name: "app",
  components: {
    MainMap
  }
};
</script>

<style>
html,
body,
#app {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
}
</style>
