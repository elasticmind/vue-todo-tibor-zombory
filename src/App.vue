<template>
  <div class="wrapper">
    <h1 class="title">To do:</h1>
    <to-do-list :items="items" @mark="handleMark" @delete="handleDelete" />
    <div class="ruler" />
    <to-do-adder @add="handleAdd" />
    <footer class="footer">Created by Tibor Zombory</footer>
  </div>
</template>

<script>
import ToDoList from "./components/ToDoList.vue";
import ToDoAdder from "./components/ToDoAdder.vue";

export default {
  data() {
    return {
      items: []
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
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  font-size: 24px;
  box-sizing: border-box;
}

.wrapper {
  background-color: #f0f0f0;
  height: 100vh;
}

.title {
  padding-top: 20px;
  padding-left: 20px;
}

.ruler {
  margin: 0 auto 20px;
  width: 80%;
  height: 2px;
  background-color: gray;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}

.footer {
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
}
</style>
