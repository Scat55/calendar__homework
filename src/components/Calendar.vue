<template>
  <div id="calendar" class="calendar">
    <div class="calendar__day" v-for="(days, idx) in calendar">
      <div class="test">
        {{ days.format('MM-YYYY') }}
        <div class="test2">{{ days.format('D') }}</div>
      </div>
    </div>
  </div>
</template>

<script>
import moment from 'moment';

export default {
  data() {
    return {
      calendar: [],
      startDay: null,
      endDay: null,
      day: null,
      totalDays: 30,
      daysArray: [...Array(42)],
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

<style lang="scss" scoped>
.calendar {
  display: grid;
  justify-content: center;

  grid-template: repeat(5, 150px) / repeat(7, 150px);
  background-color: #1e1f21;
  color: #dcdcdc;
  padding: 20px;

  &__day {
    min-width: 140px;
    min-height: 80px;
    border: 1px solid #404040;

    &:hover {
      background-color: #323337;
      cursor: pointer;
    }
  }
}
.test {
  display: flex;
  justify-content: flex-end;
}

.test2 {
  height: 33px;
  width: 33px;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
