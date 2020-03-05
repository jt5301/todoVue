<template>
  <div>
    <div v-for="todo in todoArr" v-bind:key="todo.id">
      <TodoItem v-on:del-todo="$emit('del-todo', todo.id)" v-bind:singleTodo="todo" />
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
  name: 'Todos',
  props: ['todoArr'],
  components: {
    TodoItem
  }
}
</script>

<style lang="stylus" scoped></style>


<!--line 10: accept todoArr as a prop ) -->
