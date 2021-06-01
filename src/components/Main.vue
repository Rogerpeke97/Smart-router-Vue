


<template>
  <div class="hello">
    <BackgroundOne v-bind:showSideMenu="showSideMenu"></BackgroundOne>
    <DataDisplay></DataDisplay>
  </div>
</template>

<script>
import BackgroundOne from './background/Background_1.vue';
import DataDisplay from './data/DataDisplay.vue';
export default {
  components: { BackgroundOne, DataDisplay },
  name: 'Main',
  props: {
    msg: String,
    showSideMenu: Boolean
  }
}
</script>

<style scoped>

</style>
