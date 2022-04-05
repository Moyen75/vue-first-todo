<template>
  <div v-for="task of tasks" :key="task.id">
    <SingleTask :task="task" />
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
};
</script>