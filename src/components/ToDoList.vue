<template>
  <ul class="items">
    <li class="item" v-for="(item, index) in items" :key="index">
      <div class="item-wrapper">
        <span class="text" :class="item.done && 'item--done'">
          {{ item.text }}
        </span>
        <span class="action-button mark" @click="$emit('mark', index)">
          &#10004;
        </span>
        <span class="action-button delete" @click="$emit('delete', index)">
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
.items {
  list-style-type: none;
  padding: 20px;
  margin: 0;
}

.item-wrapper {
  list-style-type: none;
  padding: 10px;
  background-color: white;
  border: 2px solid lightgray;
  border-top: unset;
  display: flex;
  flex-direction: row;
}

.item:first-child .item-wrapper {
  border-top: 2px solid lightgray;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}

.item:last-child .item-wrapper {
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
}

.action-button {
  color: white;
  cursor: pointer;
  border-radius: 7px;
}

.mark {
  background-color: rgb(66, 155, 66);
  padding: 0 7px;
  margin-left: auto;
}

.delete {
  background-color: rgb(199, 61, 61);
  padding: 0 10px;
  margin-left: 10px;
}

.item--done {
  text-decoration: line-through;
}
</style>
