<template>
  <NavigationBar></NavigationBar>

  <Footer></Footer>
</template>

<script>
import NavigationBar from "./components/NavigationBar.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    NavigationBar,
    Footer,
  },
};
</script>

<style></style>
