<template>
  <img alt="Vue logo" src="@/assets/logo.png" />
  <div class="container">
    <home-page />
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld.vue";
import HomePage from "@/components/HomePage.vue";
//const name = "alex";

export default {
  name: "App",
  components: {
    //HelloWorld,
    HomePage,
  },
};
</script>

<style>
@import "assets/style.css";
/* @import "~bootstrap/css/bootstrap.css"; */
</style>
