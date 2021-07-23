<template>
    <li>
      {{todo.todoName}}
      <button @click="$emit('doneTodo', index)">完了</button>
      <span class="todos__span" v-if="todo.done">✅</span>
    </li>
</template>

<script>
export default {
  props: {
    todo: Object,
    index: Number
  }
}
</script>
