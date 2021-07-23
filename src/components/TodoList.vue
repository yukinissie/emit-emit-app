<template>
  <ul>
    <TodoItem
      v-for="(todo, index) in todos"
      :key="index"
      :todo="todo"
      :index="index"
      @doneTodo="doneTodoHandler"
    />
  </ul>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
  props: {
    todos: Array
  },
  components: {
    TodoItem
  },
  methods: {
    doneTodoHandler(index) {
      this.$emit('doneTodoParentHandler', index)
    }
  }
}
</script>
