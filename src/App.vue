<template>
  <div id="app">
    <Calculator />
  </div>
</template>

<script>
import Calculator from "./components/Calculator.vue";

export default {
  name: "app",
  components: {
    Calculator
  }
};
</script>

<style lang="scss">

body {
  background: rgb(2,0,36);
  background: linear-gradient(145deg, rgba(2,0,36,1) 0%, rgba(254,111,111,1) 0%, rgba(89,203,89,1) 100%);
  background-size: cover;
  height: 100vh;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 100px;
}
</style>
