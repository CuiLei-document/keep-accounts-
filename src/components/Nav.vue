<template>
    <nav>
        <router-link class='item' to="/money" active-class="selected">
            <Icon name="money"/>
            金钱
        </router-link>
        <router-link class="item" to="/labels" active-class="selected">
            <Icon name="label"/>
            标签
        </router-link>
        <router-link class="item" to="/statistics" active-class="selected">
            <Icon name="conut"/>
                统计
        </router-link>
    </nav>
</template>

<script lang="ts">
    
   
    export default {
        name: 'Nav'
    };
</script>

<style lang="scss" scoped>
@import "~@/assets/style/reds.scss";
    nav{
        /*border: 1px solid red;*/
        display:flex;
        box-shadow: 0 0 3px rgba(0,0,0,0.5);
        font-size: 16px;
        > .item{
            padding: 2px 0;
            width: 33.33333%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: inherit;
            flex-direction: column;
            .con{
                width:32px;
                height: 32px;
            }
        }
        .item.selected{
            color: $color-highlight;
        }
    }
</style>