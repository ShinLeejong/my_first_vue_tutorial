<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <CanYouSeeMe message_one="can you see me now?" message_two="now you don't."/>
    <Counter />
    <DontLeaveMe />
    <DontBotherMe />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import CanYouSeeMe from './components/CanYouSeeMe.vue'
import Counter from './components/Counter.vue'
import DontLeaveMe from './components/DontLeaveMe.vue'
import DontBotherMe from './components/DontBotherMe.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    CanYouSeeMe,
    Counter,
    DontLeaveMe,
    DontBotherMe
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
