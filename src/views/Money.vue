<template>
    <Layout class-prefix="layout">
      {{record}}
      <number-pad @update:value="onUpdateAmount"></number-pad>
      <types :value.sync="record.types" ></types>
      <notes @update:value="onUpdateNotes"></notes>
      <tags :data-source.sync="tags" @update:value="onUpdateTags"></tags>
    </Layout>
</template>

<script lang="ts">
    import Vue from 'vue'
    import NumberPad from '@/components/Money/NumberPad.vue';
    import Tags from '@/components/Money/Tags.vue';
    import Notes from '@/components/Money/Notes.vue';
    import Types from '@/components/Money/Types.vue';
    import {Component} from 'vue-property-decorator';

    type Record = {
      tags: string[]
      notes: string
      types: string
      amount: number
    }

    @Component({
      components:{Types,Notes,Tags,NumberPad}
      })

    export default class Money extends Vue  {
      tags = ['衣','食','住','行']
      record: Record = {tags:[],notes:'',types:'-',amount:0}
      onUpdateTags(value:string[]){
        this.record.tags = value
      }
      onUpdateNotes(value:string){
        this.record.notes = value
      }
      onUpdateAmount(value:string){
        this.record.amount = parseFloat(value) // 将字符串转换为浮点数 number
      }
    }
</script>
<style lang="scss">
.layout-content{

  display: flex;
  flex-direction: column-reverse;
}
</style>
<style lang="scss" scoped>

</style>