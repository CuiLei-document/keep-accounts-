<template>
    <Layout class-prefix="layout">
      <number-pad></number-pad>
      <types ></types>
      <notes></notes>
      <tags :data-source="tags"></tags>
    </Layout>
</template>

<script >
    import NumberPad from '@/components/Money/NumberPad.vue';
    import Tags from '@/components/Money/Tags.vue';
    import Notes from '@/components/Money/Notes.vue';
    import Types from '@/components/Money/Types.vue';
    export default {
        name: 'Money',
      components: {Types, Notes, Tags, NumberPad},
      // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
      data(){
          return {
            tags:['衣','食','住','行']
          }
      }
    };
</script>
<style lang="scss">
.layout-content{

  display: flex;
  flex-direction: column-reverse;
}
</style>
<style lang="scss" scoped>

</style>