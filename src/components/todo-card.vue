<template>
  <div class="todo">
    <div class="header">
      <p>{{ date }}</p>
      <p id="text">VueJs Tutorial Todo Liste</p>
      <p id="tache">{{}} tache</p>
      <Newtodo />
      <TodoListe />
    </div>
  </div>
</template>



<script>
import Newtodo from "../components/Newtodo";
import TodoListe from "../components/TodoListe";

export default {
  name: "TodoCard",
  data() {
    return {
      month: ["janvier", "fevrier", "mars", "avril", "mai"],
      day: [
        "lundi",
        "mardi",
        "mercredi",
        "jeudi",
        "vendredi",
        "samedi",
        "dimanche",
      ],
    };
  },
  computed: {
    date: function () {
      let today = new Date();
      let todate =
        today.getFullYear() +
        "-" +
        `${this.month[today.getMonth()]}` +
        "-" +
        `${this.day[today.getDate() - 1]}`;
      return todate;
    },
  },
  components: {
    Newtodo,
    TodoListe,
  },
};
</script>

<style scoped>
#data {
  font-size: 22px;
}
.todo {
  background-color: orange;
}
#text {
  text-align: center;
  font-size: 24px;
}
.header #tache {
  text-align: right;
  font-size: 24px;
}
</style>