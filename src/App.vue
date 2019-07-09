<template>
  <div id="app">
    <TodoHeader />
    <router-view />
  </div>
</template>

<script>
import TodoHeader from "./components/layout/TodoHeader";
export default {
  name: "app",
  components: {
    TodoHeader
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
