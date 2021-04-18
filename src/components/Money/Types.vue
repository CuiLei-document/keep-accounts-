<template>
  <div>
    <div>
      <ul class="types">
        <li :class="type === '-' && 'selected'" @click="selectType('-')">支出</li>
        <li :class="type === '+' && 'selected'" @click="selectType('+')">收入</li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'; // 引入 vue
  import {Component,Prop} from 'vue-property-decorator'; // 告诉 typescript 一下是 vue 组件
  @Component
export default class Types extends Vue {
    type = '-' // 只能是 '-' 和 '+' 对应的是 js 的 data 函数
    @Prop(Number) xxx: number | undefined;
    selectType(type: string) { // 对应的是 js 的 methods 里面的方法
      if (type !== '-' && type !== '+') {
        throw new Error('type is unknown')
      }
      this.type = type
    }
  }


</script>

<style lang="scss" scoped>
.types{
  background: #c4c4c4;
  display: flex;
  font-size: 24px;
  > li{
    width: 50%;
    height: 64px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    &.selected::after {
      content: '';
      position: absolute;
      bottom:0;
      left:0;
      width: 100%;
      height: 4px;
      background: #333;
    }
  }
}
</style>