<template>
  <div>
    <app-navbar></app-navbar>
    <app-home></app-home>
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import Navbar from "./components/Navbar.vue";

export default {
  name: "app",
  components: {
    appHome: Home,
    appNavbar: Navbar
  }
};
</script>

<style>
@font-face {
  font-family: Geomanist-Book;
  src: url(./assets/fonts/Geomanist-Book.otf);
}
*{
  margin: 0;
  padding: 0;
}
.container{
  margin: 0 auto;
  max-width: 1366px;
  padding: 0 30px;
}
</style>
