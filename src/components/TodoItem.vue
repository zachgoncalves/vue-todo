<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}
      <button class="del" v-on:click="$emit('del-Todo', todo.id)">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
}
</script>

<style scoped>
  .todo-item {
    background:#f4f4f4;
    padding:10px;
    border-bottom:1px dotted #ccc;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background:#ff0000;
    color:#FFF;
    border:none;
    border-radius: 50%;
    padding:5px 9px;
    cursor: pointer;
    float: right;
  }
</style>
