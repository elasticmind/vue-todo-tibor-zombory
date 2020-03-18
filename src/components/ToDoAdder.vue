<template>
  <div>
    <form @submit.prevent="submit">
      <label class="labeled-input" for="task">
        <span class="input-label">
          Task
        </span>
        <input
          class="input"
          type="text"
          name="task"
          id="task"
          v-model="text"
          placeholder="What do you need to do?"
        />
      </label>
      <input class="submit" type="submit" value="Save Item" />
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: ""
    };
  },
  methods: {
    submit() {
      this.$emit("add", this.text);
      this.text = "";
    }
  }
};
</script>

<style scoped>
.labeled-input {
  display: flex;
  margin: 0 20px;
}

.input-label {
  padding: 5px 50px;
  font-weight: bold;
}

.input {
  flex-grow: 1;
  padding: 5px;
}

.submit {
  background-color: blue;
  border-radius: 10px;
  font-weight: bold;
  padding: 10px 20px;
  border: none;
  color: white;
  float: right;
  margin: 20px;
}
</style>
