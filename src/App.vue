<template>
  <NavigationBar></NavigationBar>
  <p>2 + 2 : {{ 2 + 2 }}</p>
  <p>print: {{ print() }}</p>
  <Form></Form>
  <Footer></Footer>
</template>

<script>
import NavigationBar from "./components/NavigationBar.vue";
import Footer from "./components/Footer.vue";
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: {
    NavigationBar,
    Footer,
    Form,
  },
  methods: {
    print() {
      return "a string";
    },
  },
};
</script>

<style></style>
