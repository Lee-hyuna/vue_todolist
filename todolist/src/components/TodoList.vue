<template>
  <ul>
    <li v-for="(TodoItems, TodoItemKeys) in propsdata" :key="TodoItemKeys" class="shadow">
      <span class="checkBtn">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M24 12c0-6.627-5.373-12-12-12s-12 5.373-12 12 5.373 12 12 12 12-5.373 12-12zm-18.005-1.568l1.415-1.414 4.59 4.574 4.579-4.574 1.416 1.414-5.995 5.988-6.005-5.988z"/></svg>
      </span>
      <span class="txtTodoList">{{ TodoItems }}</span>
      <span class="removeBtn" type="button" @click="removeTodo(TodoItems, TodoItemKeys)">
        <svg width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M19 24h-14c-1.104 0-2-.896-2-2v-16h18v16c0 1.104-.896 2-2 2m-9-14c0-.552-.448-1-1-1s-1 .448-1 1v9c0 .552.448 1 1 1s1-.448 1-1v-9zm6 0c0-.552-.448-1-1-1s-1 .448-1 1v9c0 .552.448 1 1 1s1-.448 1-1v-9zm6-5h-20v-2h6v-1.5c0-.827.673-1.5 1.5-1.5h5c.825 0 1.5.671 1.5 1.5v1.5h6v2zm-12-2h4v-1h-4v1z"/></svg>
      </span>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['propsdata'],
  methods: {
    removeTodo (item, idx) {
      this.$emit('removeTodo', item, idx)
    }
  }
}
</script>

<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  text-align: left;
}
li {
  display: flex;
  height: 50px;
  line-height: 50px;
  margin: 0.5rem 0;
  padding: 0 0.9rem;
  background-color: #fff;
}
.txtTodoList {
  display: block;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.checkBtn {
  margin: 8px 10px 0 0;
  cursor: pointer;
}
.removeBtn {
  margin: 7px 0 0 auto;
  cursor: pointer;
}
.list-item {
  display: inline-block;
  margin-right: 10px;
}
.list-move {
  transition: transform 1s;
}
.list-end-active, .list-leave-active {
  transition: all 1s;
}
.list-enter, .list-leave-to {
  opacity: 0;
  transform: translateY(30px)
}
</style>
