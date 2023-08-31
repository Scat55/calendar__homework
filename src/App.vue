<template>
  <div id="app">
    <div class="shadow__box">
      <Title />
      <Header class="header" :title="toDay" />
      <Calendar :calendar="calendar" />
    </div>
  </div>
</template>

<script>
import moment from 'moment';
import Header from './components/Header.vue';
import Calendar from './components/Calendar.vue';
import Title from './components/Title.vue';
export default {
  components: {
    Header,
    Calendar,
    Title,
  },
  data() {
    return {
      calendar: [],
      startDay: null,
      endDay: null,
      day: null,
      toDay: moment(),
    };
  },

  methods: {
    showDay() {
      // Начало недели начаинается с понедельника
      moment.updateLocale('en', {
        week: { dow: 1 },
      });
      // Первый день месяца и недели
      this.startDay = moment().startOf('month').startOf('week');
      // Последний день месяца и недели
      this.endDay = moment().endOf('month').endOf('week');
      this.day = this.startDay.clone();
      while (!this.day.isAfter(this.endDay)) {
        this.calendar.push(this.day.clone());
        this.day.add(1, 'day');
      }
      console.log(this.calendar);
    },
  },
  mounted() {
    this.showDay();
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
  margin-top: 50px;
}

.shadow__box {
  margin: 0 auto;
  width: 1250px;
  box-shadow: 0 0 5px 3px #000;
  border-radius: 8px;
  overflow: hidden;
}
.header {
  height: 50px;
}
</style>
