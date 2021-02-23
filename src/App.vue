<template>
  <div id="app">
    <to-do-list></to-do-list>
  </div>
</template>

<script>
import ToDoList from './components/to-do-list.vue'

export default {
  name: 'App',
  components: {
    ToDoList
  }
}
</script>

<style>
@import './assets/css/vendors/CSS Reset.css';
html, body {
  height: 100%;
}
#app {
  height: 100%;
}
</style>
