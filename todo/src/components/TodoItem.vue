<template>
  <div class="todo-item">
    <div>{{singleTodo.title}}</div>
    <div>{{singleTodo.complete}}</div>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['singleTodo']
}
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000;
  color: #f4f4f4;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>
