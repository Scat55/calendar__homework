<template>
  <div id="app">
    <Header />
    <Calendar />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Calendar from './components/Calendar.vue';
export default {
  components: {
    Header,
    Calendar,
  },
};
</script>

<style lang="scss">
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
