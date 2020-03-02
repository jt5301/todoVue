<template>
  <div id="app">
    <Todos v-bind:todoArr="todos" />
  </div>
</template>

<script>
import Todos from './components/Todos'
export default {
  name: 'App',
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'todo1',
          complete: false
        },
        {
          id: 2,
          title: 'todo2',
          complete: false
        },
        {
          id: 3,
          title: 'todo3',
          complete: false
        }
      ]
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>


<!--line 3 is using todos component, which is imported on line 8 and put in component object. Vbind: todoArr is the name of the thing we want to pass, todo in quotes refers to the data -->
