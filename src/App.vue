<template>
  <div id="app">
    <TodoList v-bind:todos="todos"/>
    <NewTodo v-on:add-todo="addTodo"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import NewTodo from './components/NewTodo';

export default {
  name: 'App',
  components: {
    TodoList,
    NewTodo,
  },
  data() {
    return {
      todos: [{
        title: 'Todo One',
        task: 'Clean my room',
        completed: false,
      }, {
        title: 'Todo Two',
        task: 'Study something meaningful',
        completed: true,
      }, {
        title: 'Todo Three',
        task: 'Write an article',
        completed: true,
      }],
    };
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        title,
        completed: false,
      });
    },
  },
};
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
