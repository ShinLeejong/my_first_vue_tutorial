<template>
  <div id="app">
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
    <button id="toggleShow" v-on:click="show = !show">toggle show!</button>
    <p v-if="show">show me!</p>
    <p v-show="show">elseif show me!</p>
    <ul id="myUl">
      <p>My hobbies:</p>
      <li v-for="(hobby, index) of Lee.hobby" v-bind:key="hobby">{{index + 1}}. {{hobby}}</li>
    </ul>
    <template v-for="text in template_is_amazing">
      <span v-bind:key="text">
        {{text}}
      </span>
    </template>
    <p>Let me introduce myself.</p>
    <template v-for="(val, key) in Lee">
      <div v-bind:key="key">
        {{key}} : {{val}}
      </div>
    </template>
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
      dynamicCSS: true,
      show: true,
      show_important: true,
      Lee: {
        name: "Lee",
        age: 27,
        hobby: ["Playing Game", "Singing"],
        email: "znlspf123@naver.com"
      },
      template_is_amazing: ["This", "is", "amazing", "!"]
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

#myUl {
  list-style: none;
  padding: 0;
}

</style>
