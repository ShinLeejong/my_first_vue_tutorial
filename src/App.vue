<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <CanYouSeeMe v-if="visible" message="can you see me now?" />
    <Button v-on:click="visible = !visible">Toggle</Button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import CanYouSeeMe from './components/CanYouSeeMe.vue'

export default {
  name: 'App',
  data: function () {
    return {
      visible: true
    }
  },
  components: {
    HelloWorld,
    CanYouSeeMe
  }
}
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
