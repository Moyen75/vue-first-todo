<template>
  <div class="container">
    <TopHeader title="Task Tracker" />
  </div>
</template>

<script>
import TopHeader from "./components/TopHeader.vue";
export default {
  name: "App",
  components: {
    TopHeader,
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  max-width: 450px;
  margin: 0 auto;
  border: 1px solid gray;
  padding: 15px;
}
</style>
