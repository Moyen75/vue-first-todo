<template>
  <div class="task-tracker">
    <h1>{{ title }}</h1>
    <AddButton title="Add Task" color="green" />
  </div>
  <AllTasks :tasks="tasks" />
</template>
<script>
import AddButton from "./AddButton.vue";
import AllTasks from "./AllTasks";
export default {
  name: "TopHeader",
  props: {
    title: String,
  },
  components: {
    AddButton,
    AllTasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  created() {
    this.tasks = [
      {
        title: "Go to Market",
        id: 1,
        time: "2:30pm",
      },
      {
        title: "Go to Bed",
        id: 2,
        time: "6:30pm",
      },
      {
        title: "Get up",
        id: 3,
        time: "3:30am",
      },
    ];
  },
};
</script>
<style scoped>
.task-tracker {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>