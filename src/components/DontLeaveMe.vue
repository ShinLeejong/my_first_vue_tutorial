<template>
    <div>
        <a v-on:click.prevent="onClick" href="https://fx-knut.github.io/fxWeb">Will you click me?</a>
    </div>
</template>
<script>
export default {
    name: "DontClickMe",
    methods: {
        onClick: function () {
            alert("Don't go there!")
        }
    }
}
</script>
<style>
    
</style>