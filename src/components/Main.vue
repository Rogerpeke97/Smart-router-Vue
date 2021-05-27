


<template>
  <div class="hello">
    <BackgroundOne v-bind:showSideMenu="showSideMenu"></BackgroundOne>
  </div>
</template>

<script>
import BackgroundOne from './background/Background_1.vue';
export default {
  components: { BackgroundOne },
  name: 'Main',
  props: {
    msg: String,
    showSideMenu: Boolean
  }
}
</script>

<style scoped>

</style>
