<template>
  <div id="app">
    <Demo  />
  </div>
</template>

<script>
import Demo from './components/demo.vue'

export default {
  name: 'App',
  components: {
    Demo
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
body,html, #app{
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #f0f0f0;
}
 
</style>
