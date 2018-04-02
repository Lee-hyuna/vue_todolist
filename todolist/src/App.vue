<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoContents></TodoContents>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoContents from './components/TodoContents.vue'

export default {
  name: 'App',
  components: {
    TodoHeader,
    TodoContents
  }
}
</script>

<style>
body {
  background-color: #f6f6f6
}
input {
  border-style: groove;
  width: 200px;
}
button {
  border-style: groove;
}
.shadow {
  box-shadow: 1px 2px 3px rgba(0,0,0,.05)
}
</style>