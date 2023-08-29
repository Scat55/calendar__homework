<template>
  <div id="app">
    <Calendar />
  </div>
</template>

<script>
import Calendar from './components/Calendar.vue';
export default {
  components: {
    Calendar,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
