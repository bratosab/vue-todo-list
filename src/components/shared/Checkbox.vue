<template>
  <div class="container" @click="check">
    <input type="checkbox" class="checkbox" v-model="checked" />
    <span class="tick"></span>
  </div>
</template>

<script>
export default {
  name: "Checkbox",
  props: ["isChecked"],
  data() {
    return {
      checked: this.isChecked
    };
  },
  methods: {
    check() {
      this.checked = !this.checked;
      this.$emit('check', this.checked);
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  position: relative;
  height: 25px;
  width: 25px;
  cursor: pointer;
}

.container .checkbox {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}
.tick {
  position: absolute;
  top: 0;
  left: 0;
  height: 25px;
  width: 25px;
  background-color: #eee;
}

.container:hover input ~ .tick {
  background: #cccccc;
}
.container input:checked ~ .tick {
  background: #007acc;
}

.container .tick:after {
  content: "";
  position: absolute;
  display: none;
}
input:checked ~ .tick:after {
  display: block;
}

.tick:after {
  left: 9px;
  top: 5px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 3px 3px 0;
  transform: rotate(45deg);
}
</style>

