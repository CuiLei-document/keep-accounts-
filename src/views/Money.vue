<template>
    <Layout class-prefix="layout">
      {{recordList}}
      <number-pad @update:value="onUpdateAmount" @submit="saveRecord"></number-pad>
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
    import {Component, Watch} from 'vue-property-decorator';

    // eslint-disable-next-line @typescript-eslint/no-var-requires
    const model = require('@/model.js').model
    console.log(model);


    @Component({
      components:{Types,Notes,Tags,NumberPad}
      })

    export default class Money extends Vue  {
      tags = ['衣','食','住','行']
      recordList  = model.fetch()
      // eslint-disable-next-line no-undef
      record: RecordItem = {tags:[],notes:'',types:'-',amount:0};
      onUpdateTags(value:string[]){
        this.record.tags = value
      }
      onUpdateNotes(value:string){
        this.record.notes = value
      }
      onUpdateAmount(value:string){
        this.record.amount = parseFloat(value) // 将字符串转换为浮点数 number
      }
      saveRecord(){
        // eslint-disable-next-line no-undef
        const record2 = model.clone(this.record)
        record2.createdAt = new Date()
        this.recordList.push(record2)
        console.log(this.recordList);
      }
      @Watch('recordList')
      onRecordListChanged(){
        model.save(this.recordList)
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