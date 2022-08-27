<template>
  <NavigationBar></NavigationBar>
  <p>2 + 2 : {{ 2 + 2 }}</p>
  <p>print: {{ print() }}</p>
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
  methods: {
    print() {
      return "a string";
    },
  },
};
</script>

<style></style>
