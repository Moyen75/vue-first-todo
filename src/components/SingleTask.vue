<template>
  <div class="task" @dblclick="$emit('toggle-reminder', task.id)">
    <div>
      <h1>{{ task.title }}</h1>
      <h3>{{ task.time }}</h3>
    </div>
    <i @click="onDelete(task.id)" class="fa-solid fa-trash-can"></i>
  </div>
</template>
<script>
export default {
  name: "SingleTask",
  props: {
    task: Object,
  },
  methods: {
    onDelete(id) {
      this.$emit("delete-task", id);
    },
  },
};
</script>
<style scoped>
h1,
h3 {
  margin: 0;
  padding: 0;
  text-align: left;
}
h3 {
  margin-left: 6px;
}
.task {
  background-color: rgba(187, 230, 216, 0.686);
  margin: 2px;
  padding: 15px;
  border-radius: 3px;
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.fa-solid {
  color: red;
}
</style>