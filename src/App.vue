<template>
  <div class="bg-slate-700 w-full h-[100vh]">
    <NavBar />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <div class="mt-14 flex flex-col justify-center items-center">
      <ResourcesBoard />
    </div>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import NavBar from "./components/NavBar.vue";
import ResourcesBoard from "./components/Resources/ResourcesBoard.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    NavBar,
    ResourcesBoard,
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
