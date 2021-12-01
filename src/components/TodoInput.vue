<template>
  <div>
    <label for="todo-input">오늘 할 일 : </label>
    <input id="todo-input" type="text" :value="item" @input="handleInput" />
    <button @click="addTodo" type="button">추가</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    item: {
      type: String,
      required: true,
    },
  },
  methods: {
    handleInput(e: InputEvent) {
      /* 
        타입 어설션!
        as 뒤의 타입이라고 개발자가 확신하며 VSCode에 이 타입임을 알린다.
        개발자가 어셜션하는 타입을 실수할 수도 있기 때문에 완전히 안전한 방식은 아니다.
      */
      const eventTarget = e.target as HTMLInputElement;
      this.$emit('input', eventTarget.value);
    },
    addTodo() {
      this.$emit('add');
    },
  },
});
</script>

<style scoped></style>
