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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 450px;
  margin: 0 auto;
  border: 1px solid gray;
}
</style>
