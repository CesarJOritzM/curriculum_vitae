<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data: function() {
    return{

    }
  },
  components: {
    HelloWorld
  }
}
</script>

<style>
</style>
