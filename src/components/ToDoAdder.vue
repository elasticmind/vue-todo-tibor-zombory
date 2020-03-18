<template>
  <div>
    <form @submit.prevent="$emit('add', text)">
      <label for="task">
        Task
        <input type="text" name="task" id="task" v-model="text" />
      </label>
      <input type="submit" value="Save Item" />
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: ""
    };
  }
};
</script>

<style scoped></style>
