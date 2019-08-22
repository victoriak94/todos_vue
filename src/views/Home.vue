<template>
  <div class="home"></div>
</template>

<script>
import Todos from "../components/Todos";
import axios from "axios";

export default {
  name: "home",
  components: {
    Todos
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(res => (this.todos = (this.todos.filter(todo => todo.id !== id)))
      .catch(err => console.log(err));
    },
    addTodo() {
      
    }
  },
  created() {
    axios
    .get("https://jsonplaceholder.typicode.com/todos?_limit=10")
    .then(res => (this.todos = res.data))
    .catch(err => console.log(err));
  }
};
</script>

<style>
</style>

