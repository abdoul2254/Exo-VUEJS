
<template>
  <div id="app"></div>
  <todo-card />
</template>

<script>
import TodoCard from "./components/todo-card";

export default {
  name: "app",
  components: {
    TodoCard,
  },
};
</script>

<style>
#app {
  background-color: rgb(207, 207, 206);
}
</style>