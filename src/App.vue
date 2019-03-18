<template>
  <div id="app">
    <Navigation />
    <div class="container">
      <Header />
      <AddTodo v-on:add-todo="addTodo" />
      <Todos v-bind:todos="todos" v-on:del-Todo="deleteTodo"></Todos>
    </div>
  </div>
</template>

<script>
import Todos from './components/Todos';
import Header from './components/layout/Header';
import AddTodo from './components/AddTodo';
import Navigation from './components/Navigation';

export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodo,
    Navigation
  },

  data() {
    return {
      todos: [
        {
          id: 1,
          title:"Todo One",
          completed: false
        },
        {
          id: 2,
          title:"Todo Two",
          completed: false
        },
        {
          id: 3,
          title:"Todo Three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos.push(newTodo);
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
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  line-height: 1.4;
}
.container {
  max-width: 700px;
  margin: 0 auto;
}
.btn {
  display: inline-block;
  border:none;
  background: #555;
  color:#FFF;
  padding:7px 20px;
  cursor: pointer;
}
.btn:hover {
  background:#666;
}
</style>
