<template>
  <div id="app">
    <todo-list/>
  </div>
</template>

<script>
import todoList from './components/todoList.vue'

export default {
  name: 'App',
  components: {
    todoList
  }
}
</script>

<style>
  body{
        background: rgb(186,226,255);
        background: linear-gradient(90deg, rgba(186,226,255,1) 0%, rgba(102,254,234,1) 100%);
    }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
