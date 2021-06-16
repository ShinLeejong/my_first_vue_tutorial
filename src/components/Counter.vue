<template>
    <div>
        <p>Counter : {{ counter }}</p>
        <button v-on:click="onClick">Click me!</button>
        <br>
        <button v-on:click="counter++">Or this way.</button>
    </div>
</template>
<script>
export default {
    name: 'Looper',
    data: function () {
        return {
            counter: 0
        }
    },
    methods: {
        onClick: function() {
            // this를 사용하여 property에 접근
            this.counter++
        }
    }
}
</script>
<style>
</style>