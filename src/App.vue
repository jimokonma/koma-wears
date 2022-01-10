<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  margin: 0px;
  padding: 0px;
  outline: none;
}
.logo {
  width: 35px;
}
.btn {
  padding: 10px;
  border: none;
  border-radius: 2px;
  background: #9dc79f;
  color: #ffffff;
  cursor: pointer;
}
.mini-btn {
  width: 20px;
  height: 20px;
  margin: 5px;
  border: none;
  background: #9dc79f;
  color: white;
}
.disabled {
  border: none;
  background: rgb(237, 237, 237);
  color: #9dc79f;
}
.small-text {
  font-size: 12px;
  color: #9dc79f;
  font-style: italic;
}
</style>
