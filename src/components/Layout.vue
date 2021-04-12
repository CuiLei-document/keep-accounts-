<template>
    <div class="layout-wrapper" :class="xxx">
        <div class="content">
            <slot></slot>
        </div>
        <Nav></Nav>
    </div>
</template>

<script lang="ts">
    export default {
      props:['xxx'],
        name: 'Layout'
    };
</script>

<style lang="scss" scoped>
    .layout-wrapper{
        display: flex;
        flex-direction: column;
        height: 100vh;
    }
    .content{
        flex-grow: 1;
        overflow: auto;
    }
</style>