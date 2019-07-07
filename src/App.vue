<template>
  <div id="app">
    <TodoHeader />
    <Add v-on:add-item="addItem" />
    <List v-bind:todos="todoItems" v-on:remove-item="removeItem" />
  </div>
</template>

<script>
import TodoHeader from "./components/layout/TodoHeader";
import Add from "./components/Add";
import List from "./components/List";

export default {
  name: "app",
  components: {
    TodoHeader,
    Add,
    List
  },
  data() {
    return {
      todoItems: [
        {
          id: 1,
          name: "Go shopping",
          completed: false
        },
        {
          id: 2,
          name: "Go to the movies",
          completed: false
        },
        {
          id: 3,
          name: "Make a dentis's appointment",
          completed: true
        }
      ]
    };
  },
  methods: {
    removeItem(id) {
      this.todoItems = this.todoItems.filter(todo => todo.id !== id);
    },
    addItem(newItem) {
      this.todoItems = [...this.todoItems, newItem];
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  background: #666666;
  color: #ffffff;
  border: none;
  padding: 6px 18px;
  cursor: pointer;
}
.btn:hover {
  background: #555555;
}
</style>
