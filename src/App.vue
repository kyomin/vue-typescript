<template>
  <div>
    <h1>Vue Todo with Typescript</h1>
    <!--
      input 컴포넌트를 따로 만들게 되면, 재활용성이 높아지면서
      사용되어지는 여러 곳에 같은 스타일과 동작을 보장할 수 있다.
    -->
    <TodoInput :item="todoText" @input="updateTodoText" @add="addTodoItem" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import TodoInput from './components/TodoInput.vue';

export default Vue.extend({
  components: {TodoInput},
  data() {
    return {
      todoText: '',
    };
  },
  methods: {
    updateTodoText(value: string) {
      this.todoText = value;
    },
    addTodoItem() {
      const value = this.todoText;
      localStorage.setItem(value, value);
      this.initTodoText();
    },
    initTodoText() {
      this.todoText = '';
    },
  },
});
</script>

<style scoped></style>
