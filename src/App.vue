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
    <div>
      <input type="text" ref="input" name="$ref_test" id="$ref_test_text" />  
      <button @click="onClick">Click Me</button>    
    </div>
    <Friends v-bind:friends="friends"/>
    <Emitter v-on:changeMessage="changeMessage($event)" />
  </div>
</template>

<script>
import CanYouSeeMe from './components/CanYouSeeMe.vue'
import Counter from './components/Counter.vue'
import DontLeaveMe from './components/DontLeaveMe.vue'
import DontBotherMe from './components/DontBotherMe.vue'
import NewWayOfDataBinding from './components/NewWayOfDataBinding.vue'
import Friends from './components/Friends.vue'
import Emitter from './components/Emitter.vue'

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
      template_is_amazing: ["This", "is", "amazing", "!"],
      friends: {
        1: "Lee",
        2: "Kim",
        3: "Park",
        4: "Gu",
        5: "Ri",
        6: "Yein",
        7: "Yiniddo"
      },
      someMessage: "Will you change me?"
    }
  },
  components: {
    // 'canYouSeeMe': CanYouSeeMe,
    CanYouSeeMe,
    Counter,
    DontLeaveMe,
    DontBotherMe,
    NewWayOfDataBinding,
    Friends,
    Emitter
  },
  methods: {
    onClick: function () {
      try {
        // $ref의 사용은 Vue의 목적(개발자가 DOM을 직접적으로 접근하지 않도록)
        // 에 어긋나므로 알고만 있고 사용은 피하자
        console.log(this.$refs);
        console.log(this.$refs.input.value);
      } catch {
        console.log("not done");
      }
    },
    changeMessage: function () {
      console.log("fired");
      window.alert("No, Never!");
    }
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

.dynamicCSS > p {
  font-size: 1.5rem;
  color: green;
}

#myUl {
  list-style: none;
  padding: 0;
}

p {
  color: violet;
}

</style>
