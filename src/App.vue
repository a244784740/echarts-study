/* eslint-disable */
<template>
  <div id="app">
    <component :is="activeChart"></component>
  </div>
</template>

<script>

import bar from './components/bar.vue';
import pileBar from './components/pileBar.vue';

export default {
  name: 'app',
  components: {
    bar,
    pileBar
  },
  data() {
    return {
      activeChart: 'pileBar'
    };
  }
}
</script>

<style>
#app {  
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(52,45,81,0);
  font-family: "Microsoft YaHei" !important;
}
</style>
