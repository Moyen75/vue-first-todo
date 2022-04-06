<template>
  <section class="form">
    <form @submit="onSubmit">
      <div>
        <label for="Add task">Add Task</label>
        <input type="text" v-model="task" placeholder="Add Task" name="task" />
      </div>
      <div>
        <label for="time">Time</label>
        <input type="text" v-model="time" placeholder="Time" name="time" />
      </div>
      <label for="checkbox">set reminder</label>
      <input class="check" v-model="reminder" type="checkbox" name="reminder" />
      <input type="submit" value="Submit now" class="btn" />
    </form>
  </section>
</template>
<script>
export default {
  name: "AddTask",
  data() {
    return {
      task: "",
      time: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      if (!this.task) {
        alert("Please add a task");
        return;
      }
      const newTask = {
        id: Math.floor(Math.random() * 10000),
        title: this.task,
        time: this.time,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);

      this.task = "";
      this.time = "";
      this.reminder = false;
    },
  },
};
</script>
<style scoped>
div {
  display: flex;
  flex-direction: column;
}
label {
  font-weight: 600;
}
input {
  display: block;
  margin: 5px;
}
.check {
  display: inline;
}
.btn {
  display: inline-block;
  margin: 0 auto;
  width: 100%;
  background-color: skyblue;
  border: none;
  border-radius: 5px;
  padding: 5px;
  font-weight: 600;
}
.form {
  padding-bottom: 10px;
  width: 100%;
}
</style>