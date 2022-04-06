<template>
  <div v-for="task of tasks" :key="task.id" class="tasks">
    <SingleTask
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :class="[task.reminder ? 'solid' : '']"
      :task="task"
    />
  </div>
</template>
<script>
import SingleTask from "./SingleTask.vue";
export default {
  name: "AllTasks",
  props: {
    tasks: Array,
  },
  components: {
    SingleTask,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
<style scoped>
.solid {
  position: relative;
}
.solid::before {
  position: absolute;
  left: 0;
  height: 100%;
  width: 3px;
  content: "";
  background-color: #45924f;
  top: 0;
  bottom: 0;
}
</style>