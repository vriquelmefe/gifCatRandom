<template>
  <div id="app">
    <GitCat msg="Random Gif Cat" />
  </div>
</template>

<script>
import GitCat from "./components/GitCat.vue";

export default {
  name: "App",
  components: {
    GitCat,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #090a0c;
}
body{
  margin: 0;
  padding: 0;
  border: 0;
  background-color: rgb(139, 184, 230);
}
</style>
