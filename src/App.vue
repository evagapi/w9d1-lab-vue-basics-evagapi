<template>
  <NavigationBar></NavigationBar>
  <main class="px-16 py-8 bg-white">
    <p class="bg-teal-100 p-4 mb-8">2 + 2 : {{ 2 + 2 }}</p>
    <p class="bg-pink-100 p-4 mb-8">print: {{ print() }}</p>
    <Form></Form>
  </main>
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
