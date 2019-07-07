<template>
  <div id="app">
    <List v-bind:todos="todos" />
  </div>
</template>

<script>
import List from "./components/List";

export default {
  name: "app",
  components: {
    List
  },
  data() {
    return {
      todos: [
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
</style>
