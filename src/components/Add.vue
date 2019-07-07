<template>
  <div>
    <form @submit="addItem">
      <input type="text" name="name" v-model="name" placeholder="New item..." />
      <input type="submit" value="Add item" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "Add",
  data() {
    return {
      name: ""
    };
  },
  methods: {
    addItem(e) {
      e.preventDefault();
      const newItem = {
        name: this.name,
        completed: false
      };

      this.$emit("add-item", newItem);

      this.name = "";
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 1;
}
input[type="submit"] {
  width: 80px;
}
</style>
