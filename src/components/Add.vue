<template>
  <div>
    <form>
      <input type="text" name="title" placeholder="New item..." />
      <input type="submit" value="Add" class="add-btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "Add"
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 1;
  padding: 4px;
}
input[type="submit"] {
  padding: 4px;
}
</style>
