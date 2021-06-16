<template>
    <div class="CanYouSeeMe" v-if="CanYouSeeMe">
        {{ message }}
    </div>
</template>
<script>
export default {
    name: 'CanYouSeeMe',
    props: {
        message: String
    },
    data: function() {
        return {
                CanYouSeeMe: true
            };
    }
}
</script>
<style>
    
</style>