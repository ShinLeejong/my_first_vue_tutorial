<template>
    <div>
        <button v-on:click.once="onClick">{{ message }}</button>
    </div>
</template>
<script>
export default {
    name: "DontBotherMe",
    data: function () {
        return {
           message: "Don't try to BOTHER me!!"
        }
    },
    methods: {
        onClick: function() {
            this.message += " NO!!!"
            console.log("onClick fired on DontBotherMe")
        }
    }
}

</script>
<style>
    
</style>

