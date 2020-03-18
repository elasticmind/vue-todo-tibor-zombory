<template>
  <div>
    <to-do-list :items="items" @mark="handleMark" @delete="handleDelete" />
    <to-do-adder @add="handleAdd" />
  </div>
</template>

<script>
import ToDoList from "./components/ToDoList.vue";
import ToDoAdder from "./components/ToDoAdder.vue";

export default {
  data() {
    return {
      items: [
        {
          text: "text1",
          done: true
        },
        {
          text: "text2",
          done: true
        },
        {
          text: "text3",
          done: false
        }
      ]
    };
  },
  components: {
    ToDoList,
    ToDoAdder
  },
  methods: {
    handleMark(payload) {
      this.items[payload].done = !this.items[payload].done;
    },
    handleDelete(payload) {
      this.items.splice(payload, 1);
    },
    handleAdd(payload) {
      this.items.push({ text: payload, done: false });
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
