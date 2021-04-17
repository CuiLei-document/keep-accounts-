<template>
    <Layout class-prefix="layout">
      <number-pad></number-pad>
      <types xxx="hi"></types>
      <notes></notes>
      <tags></tags>
    </Layout>
</template>

<script lang="ts">
    import NumberPad from '@/components/Money/numberPad.vue';
    import Tags from '@/components/Money/Tags.vue';
    import Notes from '@/components/Money/Notes.vue';
    import Types from '@/components/Money/Types.vue';
    export default {
        name: 'Money',
      components: {Types, Notes, Tags, NumberPad}
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