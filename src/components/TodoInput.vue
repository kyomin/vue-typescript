<template>
  <div>
    <label for="todo-input"></label>
    <input id="todo-input" type="text" :value="item" @input="handleInput" />
    <button @click="addTodo" type="button">추가</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: ['item'],
  methods: {
    handleInput(e: any) {
      this.$emit('input', e.target.value);
    },
    addTodo() {
      console.log('addTodo');
    },
  },
});
</script>

<style scoped></style>
