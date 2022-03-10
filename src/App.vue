<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import liff from "@line/liff";
export default {
  name: "App",
  components: {
    HelloWorld,
  },
  mounted() {
    this.initLiff();
  },
  methods: {
    initLiff() {
      liff
        .init({ liffId: process.env.VUE_APP_LIFFID })
        .then(() => {
          console.log("Success! you can do something with LIFF API here.");
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
