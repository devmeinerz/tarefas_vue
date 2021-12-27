<template>
  <div id="app">
    <header>Minhas tarefas</header>
    <Task/>
  </div>
</template>

<script>
import Task from './components/Task';
export default {
  name: "App",
  components: {
    Task,
  },
};
</script>

<style scoped>

#app header{
  font-family: Roboto Condensed, sans-serif;
  font-weight: bold;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
  font-size: 50px;
}
</style>
