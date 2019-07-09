<template>
  <header class="header">
    <h1>Vue.js Todo List</h1>
    <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "TodoHeader"
};
</script>

<style scoped>
.header {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 5px;
  background-color: #007acc;
  color: #ffffff;
}
.header a {
  text-decoration: none;
  color: #ffffff;
}
.header a:not(:last-of-type):after {
  content: " | ";
}
</style>
