<template>
<div>
  <div class="tags">
    <div class="new">
      <button @click="create">新增标签</button>
    </div>
    <ul class="current">
      <li v-for="tag in dataSource" :key="tag" @click="taggle(tag)"
      :class="{selected: selectedTag.indexOf(tag)>=0 }">{{tag}}</li>
    </ul>
  </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue';
import {Component,Prop} from 'vue-property-decorator';
@Component
export default class Tags extends Vue{
  @Prop(Array) dataSource:string[] | undefined;
  selectedTag:string[] =[]
  // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
  taggle(tag:string){
    const index = this.selectedTag.indexOf(tag)
    if (index >=0){
      this.selectedTag.splice(index,1)
    }else{
     this.selectedTag.push(tag)
    }
    this.$emit('update:value',this.selectedTag)
  }
  create(){
    const name = window.prompt('请输入添加的标签')
    if(name === ''){
      window.alert('标签不能为空')
    }else if(this.dataSource){
      this.$emit('update:dataSource',[...this.dataSource,name])
    }
  }

}
</script>

<style lang="scss" scoped>
.tags{
  font-size: 14px;
  padding: 16px;
  flex-grow: 1;
  display: flex;
  flex-direction: column-reverse;
  > .current{
    display: flex;
    > li{
      $bg: #d9d9d9;
      background: $bg;
      $h: 24px;
      height: $h;
      line-height: $h;
      border-radius: $h/2;
      padding: 0 16px;
      margin-right: 12px;
      &.selected{
        background: darken($bg,50%);
        color: white;
      }
    }
  }
  > .new {
    padding-top: 16px;
    button{
      background: transparent;
      border: none;
      color: #999;
      border-bottom: 1px solid ;
      padding: 0 3px;
    }
  }
}
</style>