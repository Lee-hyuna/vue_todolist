<template>
  <div class="inpBox">
    <input type="text" v-model="newTodoItem" placeholder="What needs to be done?" v-on:keyup.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M24 9h-9v-9h-6v9h-9v6h9v9h6v-9h9z"/></svg></span>

    <modal v-if="showModal" @close="showModal = false">
      <h3 slot="header">Warning</h3>
      <span slot="footer" @click="showModal = false">
        Enter work to do!!
        <span class="modal-default-button" aria-hidden="true">OK</span>
      </span>
    </modal>
  </div>
</template>

<script>
import Modal from './common/Modal.vue'

export default {
  data () {
    return {
      newTodoItem: '',
      showModal: false
    }
  },
  methods: {
    addTodo () {
      if (this.newTodoItem !== '') {
        var value = this.newTodoItem && this.newTodoItem.trim()
        this.$emit('addTodo', value)
        this.clearInput()
      }else {
        this.showModal = !this.showModal;
        // 텍스트 미입력시 모달팝업 동작
      }
    },
    clearInput () {
      this.newTodoItem = ''
    }
  },
  components : {
    Modal: Modal
  }
}
</script>

<style>
input:focus {
  outline: none
}
.inpBox {
  position: relative;
  background-color: #fff;
  height: 50px;
  line-height: 50px;
}
.inpBox input {
  width: 100%;
  border-style: none;
  font-size: 0.9rem;
  padding: 0 70px 0 30px;
  height: 100%;
  box-sizing: border-box;
}
.addContainer {
  position: absolute;
  top: 0;
  right: 0;
  height: 50px;
  background-color: #95d0da;
  box-sizing: border-box;
  padding: 6px 12px 0;
  cursor: pointer;
}
.modal-default-button {
  color: red;
  font-size: 12px;
  cursor: pointer;
}
</style>