<template>
  <div id="app">
    <Header />
    <AddToDo v-on:add-todo="addToList" />
    <Todos v-bind:todoArr="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos'
import AddToDo from './components/AddToDo'
import Header from './components/Layout/Header'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddToDo
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(() => {
          this.todos = this.todos.filter(current => {
            return current.id != id
          })
        })
        .catch(error => {
          console.log(error)
        })
    },
    addToList(payload) {
      const {title, completed} = payload
      axios
        .post('https://jsonplaceholder.typicode.com/todos', {
          title,
          completed
        })
        .then(res => {
          this.todos = [...this.todos, res.data]
        })
        .catch(error => console.log(error))
    }
  },
  created() {
    axios
      .get('https://jsonplaceholder.typicode.com/todos?_limit=10')
      .then(res => {
        this.todos = res.data
      })
      .catch(err => {
        console.log(err)
      })
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
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>


<!--line 3 is using todos component, which is imported on line 8 and put in component object. Vbind: todoArr is the name of the thing we want to pass, todo in quotes refers to the data
line 35 created is similar to component did mount
      https://jsonplaceholder.typicode.com/todos
 -->
