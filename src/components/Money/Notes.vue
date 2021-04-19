<template>
<div>
  <div>
    <label class="notes">
      {{value}}
      <span class="name">备注</span>
      <input type="text" :value="value"  @input="onInput" placeholder="请在这里输入备注">
    </label>
  </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue';
import {Component} from 'vue-property-decorator';
@Component
export default class Notes extends Vue{
 value = ''
  // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
  onInput(event: KeyboardEvent){
    this.value = event.target.value
  }
}
</script>

<style lang="scss" scoped>
.notes{
  font-size: 14px;
  background: #f5f5f5;
  display: flex;
  align-items: center;
  padding-left: 16px;
  .name{
    padding-right: 16px;
  }
  input{
    height: 64px;
    flex-grow: 1;
    background: transparent;
    border: none;
    padding-right: 16px;
  }
}
</style>