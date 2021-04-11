<template>
    <div class="nav-labels">
        <div class="content">
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
            <p>我是Labels.vue</p>
        </div>
        <Nav></Nav>
    </div>
</template>

<script lang="ts">
    export default {
        name: 'Labels'
    };
</script>

<style lang="scss" scoped>
    .nav-labels{
        border: 1px solid green;
        display: flex;
        flex-direction: column;
        height: 100vh;
    }
    .content{
        overflow: auto;
        flex-grow: 1;
    }
</style>