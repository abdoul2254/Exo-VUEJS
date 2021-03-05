<template>
  <div>
    <input v-model="tache" type="text" />
    <button v-on:click="sendTask(tache)">ajouter</button>
    <p>{{ tache }}</p>
  </div>
</template>
<script>
export default {
  name: "Newtodo",

  data() {
    return {
      tache: ["la tache"],
      counter: 0,
    };
  },
  methods: {
    sendTask(Tache) {
      if (Tache != null) {
        this.$emit("NewTask", Tache);
      }
    },
  },
};
</script>




<style scoped>
#liste {
  text-align: left;
}
</style>