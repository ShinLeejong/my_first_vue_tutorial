<template>
    <div>
        <div class="CanYouSeeMe" v-if="CanYouSeeMe">
            {{ message_one }}
        </div>
        <div class="CanYouSeeMe">
            {{ message_two }}
        </div>
        <button v-on:click="onClick">Toggle</button>
    </div>
</template>
<script>
export default {
    name: 'CanYouSeeMe',
    props: {
        message_one: String,
        message_two: String
    },
    data: function() {
        return {
                CanYouSeeMe: true,
            };
    },
    methods: {
        onClick: function () {
            this.CanYouSeeMe = !this.CanYouSeeMe
        }
    }
}
</script>
<style>
    
</style>