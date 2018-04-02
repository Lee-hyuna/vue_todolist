<template>
  <div class="clearAllContainer">
    <span class="clearAllBtn" @click="clearTodo">Clear All</span>
  </div>
</template>

<script>
export default {
  methods: {
    clearTodo () {
      this.$emit('removeAll');
    }
  }
}
</script>

<style>
.clearAllBtn {
  cursor: pointer;
}
</style>