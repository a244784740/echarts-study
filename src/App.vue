/* eslint-disable */
<template>
  <div id="app">
    <bar></bar>
  </div>
</template>

<script>

import bar from './components/bar.vue';

export default {
  name: 'app',
  components: {
    bar
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
