<template>
  <div>
    <header class="header">
        <h1>TodoList</h1>
    </header>
    <AddTodo v-on:add-todo="addTodo" />
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-on:del-Todo="deleteTodo(todo.id)"/>
    </div>
  </div>
</template>
<script>
import TodoItem from './TodoItem';
import AddTodo from './AddTodo';

export default {
  name: "Todos",
  components: {
    TodoItem, 
    AddTodo
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
  .header {
    background:#A41E35;
    color:#FFF;
    text-align: center;
    padding:10px;
    margin-top: 3rem;
  }
  .header a {
    color:#FFF;
    padding-right: 5px;
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
