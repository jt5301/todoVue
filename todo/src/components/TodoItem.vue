<template>
  <div class="todo-item" v-bind:class="{'is-complete':singleTodo.complete}">
    <p>
      <input type="checkbox" v-on:change="markComplete" />
      {{singleTodo.title}}
      <button class="del">delete</button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['singleTodo'],
  methods: {
    markComplete() {
      this.singleTodo.complete = !this.singleTodo.complete
    }
  }
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
<!--
line 2: v-bind binds the class 'iscomplete' depending on if singletodo.complete evaluates to true or not
line 4: v-on listens to dom events and will listen for a change event, which will then run the method markcomplete
 -->
