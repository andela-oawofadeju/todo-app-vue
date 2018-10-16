<template>
  <div id="app">
    <h1 class='ui dividing center header'>Todo app for learning</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <TodoList v-bind:todos="todos"/>
        <NewTodo v-on:add-todo="addTodo"/>
      </div>
    </div>
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
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
  watch: {
    todos: {
      handler() {
        localStorage.todos = JSON.stringify(this.todos);
      },
      deep: true,
    },
  },
  mounted() {
    if (localStorage.todos) {
      this.todos = JSON.parse(localStorage.todos);
    }
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
      sweetalert('Success!', 'New Todo Created!', 'success');
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
