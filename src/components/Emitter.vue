<template>
    <div>
        <h3>{{someMessage}}</h3>
        <button id="alertBtn" v-on:click="emitter">Altar</button>
    </div>
</template>
<script>
export default {
    name: "alertBtn",
    data: function () {
        return {
            someMessage: "Will you change me?"
        }
    },
    methods: {
        emitter: function () {
            this.$emit('changeMessage');
        }
    }
}
</script>
<style>
    
</style>