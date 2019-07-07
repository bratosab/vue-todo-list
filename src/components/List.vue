<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <Item v-bind:todo="todo" />
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
