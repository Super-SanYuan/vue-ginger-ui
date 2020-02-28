<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <hr />
    <g-button type="primary" @click="onClick" id="btn"> Click </g-button>
    <g-button type="dashed" @click="onClick" id="btn"> Click </g-button>
    <g-button @click="onClick" id="btn"> Click </g-button>
  </div>
</template>

<script>
export default {
  name: "app",
  methods: {
    onClick() {
      console.log("click被触发");
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
