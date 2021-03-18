<template>
  <Employees />
</template>

<script>
import Employees from './components/Employees.vue'

export default {
  name: 'App',
  components: {
    Employees
  }
}
</script>

<style>
body {
  background-color: #16a085;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 1rem auto;
  width: 700px;
}
</style>