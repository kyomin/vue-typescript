<template>
  <div>
    <label for="todo-input"></label>
    <input id="todo-input" type="text" />
    <button @click="addTodo" type="button">추가</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  methods: {
    addTodo() {
      console.log("addTodo");
    },
  },
});
</script>

<style scoped>
</style>