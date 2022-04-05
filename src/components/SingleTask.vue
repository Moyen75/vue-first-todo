<template>
  <h1>{{ task.title }}</h1>
  <h3>{{ task.time }}</h3>
</template>
<script>
export default {
  name: "SingleTask",
  props: {
    task: Object,
  },
};
</script>