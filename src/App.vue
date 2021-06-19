<template>
  <div id="app">
    <div id="bag_image_container">
    </div>
    <div id="bag-healthbar">
      <div id="bag-healthbar-health" v-bind:style="{ width: health + '%' }">
      </div>
    </div>
    <div id="bag-punch_restart">
      <button v-if="health !== 0" v-on:click.prevent="punch">Punch!</button>
      <button v-on:click.prevent="restart">Restart</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: function () {
    return {
      health: 100
    }
  },
  methods: {
    punch: function () {
      this.health -= 5
    },
    restart: function () {
      this.health = 100
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

#bag_image_container {
  width: 25rem;
  height: 30rem;
  margin: 0 auto;
  background: url(assets/punchbag.jpg);
  background-repeat: no-repeat;
}

#bag-healthbar {
  margin: 0 auto;
  width: 20rem;
  height: 1.5rem;
  border: 5px solid black;
  margin: 0 auto 2rem auto;
}

#bag-healthbar-health {
  height: 100%;
  background-color: red;
}

button {
  margin: 1rem 1rem;
}

</style>
