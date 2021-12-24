<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <ExpenseTracker />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import ExpenseTracker from "./components/ExpenseTracker.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    ExpenseTracker,
  },
};
</script>

<style>
body {
  background: #515151;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  color: #fff;
}
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
