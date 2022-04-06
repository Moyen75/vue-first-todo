<template>
  <div class="task-tracker">
    <h1>{{ title }}</h1>
    <AddButton
      @show-addTask="showTask"
      :title="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'yellow' : 'green'"
    />
  </div>
  <AddTask v-if="showAddTask" @add-task="addTask" />
  <AllTasks
    @delete-task="deleteTask"
    @toggle-reminder="toggle"
    :tasks="tasks"
  />
</template>
<script>
import AddTask from "./AddTask.vue";
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
    AddTask,
  },
  methods: {
    showTask() {
      this.showAddTask = !this.showAddTask;
    },
    deleteTask(id) {
      if (confirm("Are you sure to delete this?"))
        this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    toggle(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
  },
  data() {
    return {
      tasks: [],
      showAddTask: false,
    };
  },
  created() {
    this.tasks = [
      {
        title: "Go to Market",
        id: 1,
        time: "2:30pm",
        reminder: true,
      },
      {
        title: "Go to Bed",
        id: 2,
        time: "6:30pm",
        reminder: true,
      },
      {
        title: "Get up",
        id: 3,
        time: "3:30am",
        reminder: false,
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