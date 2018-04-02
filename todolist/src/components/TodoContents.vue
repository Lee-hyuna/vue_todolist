<template>
  <div>
    <TodoInput v-bind:propsdata="todoItems" v-on:addTodo="addTodo"></TodoInput>
    <TodoList v-bind:propsdata="todoItems" @removeTodo="removeTodo"></TodoList>
    <TodoFooter v-on:removeAll="clearAll"></TodoFooter>
  </div>
</template>

<script>
import TodoInput from './TodoInput.vue'
import TodoList from './TodoList.vue'
import TodoFooter from './TodoFooter.vue'

export default {
  data () {
    return {
      todoItems: []
    }
  },
  created () {
    if (localStorage.length > 0) {
      // 로컬스토리지에 저장된 모든 아이템을 한번에 불러오는 API는 없기 때문에 배열로 불러와야 함.
      for (var i = 0, len = localStorage.length; i < len; i++) {
        this.todoItems.push(localStorage.key(i))
      }
    }
  },
  methods: {
    addTodo (todoItem) {
      // 로컬 스토리지에 데이터를 추가하는 로직
      localStorage.setItem(todoItem, todoItem)
      this.todoItems.push(todoItem)
    },
    clearAll () {
      localStorage.clear()
      this.todoItems= []
    },
    removeTodo (todoItem, index) {
      localStorage.removeItem(todoItem)
      this.todoItems.splice(index, 1)
    }
  },
  components: {
    'TodoInput': TodoInput,
    'TodoList': TodoList,
    'TodoFooter': TodoFooter
  }
}
</script>