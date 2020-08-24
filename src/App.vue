<template>
  <div id="app">
    <HelloWorld msg />
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>
<style>
#app {
  font-family: "Bungee", cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffd900;
  margin-top: 60px;
  background: url(https://media.gizmodo.co.uk/wp-content/uploads/2013/05/18oiwrk32uilpgif.gif)
    no-repeat center fixed;
  background-size: cover;
}
i1 {
  color: orange;
  font-size: 35px;
  text-shadow: 2px 2px 5px red;
}
p {
  color: rgb(255, 2, 2);
  font-size: 35px;
  text-shadow: 2px 2px 5px yellow;
}
</style>
