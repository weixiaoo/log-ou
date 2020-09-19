<template>
  <div id="app">
    <log></log>
  </div>
</template>

<script>
import Log from './components/Log.vue'

export default {
  name: 'App',
  components: {
    Log
  }
}
</script>

<style>
  @import './assets/css/base.css';
  #app {
    position: relative;
    height: 100%;
    width: 100%;
  }
</style>
