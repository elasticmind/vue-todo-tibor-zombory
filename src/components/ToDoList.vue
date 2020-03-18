<template>
  <ul>
    <li v-for="(item, index) in items" :key="index">
      <div class="item-wrapper">
        <span :class="item.done && 'item--done'">
          {{ item.text }}
        </span>
        <span @click="$emit('mark', index)">
          &#10004;
        </span>
        <span @click="$emit('delete', index)">
          x
        </span>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      default: () => []
    }
  }
};
</script>

<style scoped>
.item--done {
  text-decoration: line-through;
}
</style>
