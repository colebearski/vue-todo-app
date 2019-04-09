<template>
  <div id="app">
    <Todos v-bind:todos="todos"/>
  </div>
  <!-- get our todos into the todos component -->
</template>


<script>
import Todos from "./components/Todos";

export default {
  name: "app",
  components: {
    Todos
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
          completed: true
        },
        {
          id: 3,
          title: "Be awesome",
          completed: false
        }
      ]
    };
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
</style>
