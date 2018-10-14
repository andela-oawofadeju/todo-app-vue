<template>
  <div id="app">
    <TodoList v-bind:todos="todos"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList';

export default {
  name: 'App',
  components: {
    TodoList,
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
