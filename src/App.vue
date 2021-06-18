<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <CanYouSeeMe message_one="can you see me now?" message_two="now you don't."/>
    <Counter />
    <DontLeaveMe />
    <DontBotherMe />
    <NewWayOfDataBinding />
    <div id="colored_one" v-bind:class="{red:true, blue:false}">
      <p>hi!</p>
    </div>
    <div id="colored_two" v-bind:class="{dynamicCSS: dynamicCSS}">
      <button v-on:click="dynamicCSS = !dynamicCSS">click me to toggle color</button>
      <p>hi there!</p>
    </div>
  </div>
</template>

<script>
import CanYouSeeMe from './components/CanYouSeeMe.vue'
import Counter from './components/Counter.vue'
import DontLeaveMe from './components/DontLeaveMe.vue'
import DontBotherMe from './components/DontBotherMe.vue'
import NewWayOfDataBinding from './components/NewWayOfDataBinding.vue'

export default {
  name: 'App',
  data: function () {
    return {
      dynamicCSS: true
    }
  },
  components: {
    CanYouSeeMe,
    Counter,
    DontLeaveMe,
    DontBotherMe,
    NewWayOfDataBinding
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

.red {
  color: red;
}

.blue {
  color: blue;
}

.dynamicCSS > p {
  font-size: 1.5rem;
  color: green;
}

</style>
