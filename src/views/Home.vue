<template>
  <div class="home"></div>
</template>

<script>
import Todos from "../components/Todos";

export default {
  name: "home",
  components: {
    Todos
  },
  data() {
    return {
      todos: []
    };
  }
};
</script>

<style>
</style>

