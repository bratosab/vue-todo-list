<template>
  <div id="app">
    <Add v-on:add-item="addItem" />
    <List v-bind:todos="todoItems" v-on:remove-item="removeItem" />
  </div>
</template>

<script>
import Add from "../components/Add";
import List from "../components/List";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Add,
    List
  },
  data() {
    return {
      todoItems: []
    };
  },
  methods: {
    removeItem(id) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then((this.todoItems = this.todoItems.filter(todo => todo.id !== id)))
        .catch(err => console.error(err));
    },
    addItem(newItem) {
      const { name, completed } = newItem;

      axios
        .post("https://jsonplaceholder.typicode.com/todos", {
          title: name,
          completed
        })
        .then(
          res =>
            (this.todoItems = [
              ...this.todoItems,
              { ...res.data, name: res.data.title }
            ])
        )
        .catch(err => console.error(err));
    }
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=10")
      .then(
        res =>
          (this.todoItems = res.data.map(d => {
            return { ...d, name: d.title };
          }))
      )
      .catch(err => console.error(err));
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
