<template>
  <div id="todo-list-example">
    <form v-on:submit.prevent="addNewTodo">
      <label for="new-todo">Ajouter une tâche</label>
      <input v-model="newTodoText" id="new-todo" placeholder="Mes taches" />
      <button>Add</button>
    </form>
    <ul>
      <li
        v-for="(todo, index) in todos"
        v-bind:key="todo.id"
        v-bind:title="todo.title"
        v-on:remove="todos.splice(index, 1)"
      ></li>
    </ul>
  </div>
  <TodoListe />
</template>
<script>
import TodoListe from "./TodoListe.vue";
export default {
  name: "Newtodo",
  components: {
    TodoListe,
  },
  data() {
    return {
      mesg: "la tache",
      todos: [
        {
          id: 1,
          title: "Tache 1",
        },
        {
          id: 2,
          title: "Tache 2",
        },
        {
          id: 3,
          title: "Tache 3",
        },
      ],
    };
  },
  methods: {
    addNewTodo: function () {
      this.todos.push({
        id: this.nextTodoId++,
        title: this.newTodoText,
      });
      this.newTodoText = "";
    },
  },
};
</script>




<style scoped>
#liste {
  text-align: left;
}
</style>