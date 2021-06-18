<template>
    <div>
        <input type="text" v-model="newText" v-on:change="setNewText" >
    </div>
</template>
<script>
export default {
    name: 'newText',
    data: function () {
        return {
            newText: ''
        }
    },
    methods: {
        setNewText: function (e) {
            // 입력을 모두 마치고 엔터를 누르거나 focus가 빠질 때
            // 함수가 호출됨
            this.newText = e.target.value
            console.log(this.newText);
        }
    }
}
</script>
<style>
 
</style>