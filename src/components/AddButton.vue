<template>
  <div>
    <button :style="{ background: color }">{{ title }}</button>
  </div>
</template>
<script>
export default {
  name: "AddButton",
  props: {
    title: String,
    color: String,
  },
};
</script>
<style scoped>
button {
  background: black;
  border-radius: 7px;
  color: white;
  margin-left: 10px;
}
</style>