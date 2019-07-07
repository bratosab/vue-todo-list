<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <Item v-bind:todo="todo" v-on:remove-item="$emit('remove-item', todo.id)" />
    </div>
  </div>
</template>

<script>
import Item from "./Item";

export default {
  name: "List",
  components: { Item },
  props: ["todos"]
};
</script>

<style scoped>
</style>
