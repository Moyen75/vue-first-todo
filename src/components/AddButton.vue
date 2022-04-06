<template>
  <div>
    <button @click="onClick()" :style="{ background: color }">
      {{ title }}
    </button>
  </div>
</template>
<script>
export default {
  name: "AddButton",
  props: {
    title: String,
    color: String,
  },
  methods: {
    onClick() {
      this.$emit("show-addTask");
    },
  },
};
</script>
<style scoped>
button {
  border-radius: 5px;
  padding: 8px;
  margin-left: 10px;
  font-weight: 700;
  border: none;
}
</style>