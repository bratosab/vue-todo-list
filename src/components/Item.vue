
<template>
  <div class="item" v-bind:class="{'completed':todo.completed}">
    <Checkbox v-bind:isChecked="todo.completed" v-on:check="changeCompletionState" />
    <p>{{ todo.name }}</p>
    <button @click="$emit('remove-item', todo.id)" class="remove-btn">delete</button>
  </div>
</template>

<script>
import Checkbox from "./shared/Checkbox";

export default {
  name: "item",
  props: ["todo"],
  components: { Checkbox },
  methods: {
    changeCompletionState() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 8px;
  background: #f6f6f6;
}
p {
  flex: 1;
  padding: 0 6px;
}
.completed {
  opacity: 0.4;
}
.remove-btn {
  padding: 5px;
  border-radius: 50%;
  cursor: pointer;
}
</style>
