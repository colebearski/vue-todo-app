<template>
  <div id="app">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>


<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
import Header from "./components/layout/Header";

export default {
  name: "app",
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Make Vue Todo app",
          completed: false
        },
        {
          id: 2,
          title: "Put this wicked app on GH",
          completed: false
        },
        {
          id: 3,
          title: "Be awesome",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      // basically loops thru an array using a condition and returns every iteration that meets condition
      this.todos = this.todos.filter(todo => todo.id !== id);
    },

    addTodo(newTodo) {
      // spread operator to copy all current todos and then add a new todo
      this.todos = [...this.todos, newTodo];
    }
  }
};
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
</style>
