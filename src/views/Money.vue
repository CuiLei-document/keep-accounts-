<template>
    <div class="nav-money">
        <div class="content">
            <div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div><div>我是Money.vue</div>
        </div>
        <Nav></Nav>
    </div>
</template>

<script lang="ts">
    export default {
        name: 'Money'
    };
</script>

<style lang="scss" scoped>
    .nav-money{
        border:1px solid blue;
        display: flex;
        flex-direction: column;
        height:100vh
    }
    .content{
        overflow: auto;
        flex-grow: 1;
    }
</style>