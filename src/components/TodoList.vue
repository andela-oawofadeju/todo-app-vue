<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo=>{return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo=>{return todo.done === false}).length}}</p>
    <Todo  v-for="todo in todos" v-bind:todo="todo" :key="todo.id"/>
  </div>
</template>
<script type="text/javascript">
import Todo from './Todo';

export default{
  props: ['todos'],
  components: {
    Todo,
  },
};
</script>
<style>
</style>
