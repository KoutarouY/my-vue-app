<template>
  <div id="app">
    <div class="hello-world">
      <img alt="Vue logo" src="./assets/logo.png" />
      <div class="hello-world__message">{{ message }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  deta: function () {
    return {
      message: "WebExpert Course Vue Template",
    }
  },
  methods: {},
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>

<style scoped>
.hello-world {
  margin-top: 60px;
  text-align: center;
}
.hello-wrold .hello-world__message {
  color: #2c3e50;
}
</style>
