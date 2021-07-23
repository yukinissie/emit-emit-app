<template>
  <div>
    <input
      v-model="todoName"
    />
    <button @click="addTodo">追加</button>
    <TodoList
      :todos='todos'
      @doneTodoParentHandler='doneTodo'
    />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  components: {
    TodoList
  },
  data() {
    return {
      todoName: "",
      todos: []
    }
  },
  methods: {
    addTodo() {
      if (this.todoName) {
        this.todos.push({
          todoName: this.todoName,
          done: false
        })
        this.todoName = ""
      }
    },
    doneTodo(index) {
      this.todos[index].done = !this.todos[index].done
    }
  }
}
</script>
