<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo=>{return todo.completed === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo=>{return todo.completed === false}).length}}</p>
    <Todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo"
      v-for="todo in todos" :key="todo.id" :todo.sync="todo"/>
  </div>
</template>
<script type="text/javascript">
import Todo from './Todo';

export default{
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todo[todoIndex].completed = true;
    },
  },
};
</script>
<style>
</style>
