<template>
    <div id="friends">
        <ul>
            <p>My friends list below.</p>
            <li v-for="(val, key) in friends" v-bind:key="key">
                <h4>{{key}}. {{val}}</h4>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    props: {
        friends: {
            type: Object,
            required: true
        }
    },
    data: function () {
        return {

        }
    }
}
</script>
<style scoped>
    p {
        color: brown;
    }
    h4 {
        margin: unset;
    }
    li {
        list-style: none;
    }
</style>