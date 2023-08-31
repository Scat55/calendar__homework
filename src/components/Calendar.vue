<template>
  <div id="calendar" class="calendar">
    <div
      class="calendar__day"
      v-for="(days, idx) in calendar"
      :class="days.day() === 6 || days.day() === 0 ? 'week' : ''"
    >
      <div class="test">
        <div class="test2 toDay" v-if="currentDay(days)">
          {{ days.format('D') }}
        </div>

        <div class="test2" v-else="!currentDay(days)">
          {{ days.format('D') }}
        </div>
      </div>
      <!-- <div class="calendar__event">{{ event[0].title }}</div> -->
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import moment from 'moment';
export default {
  props: {
    calendar: {
      type: Array,
      default: [],
    },
    isWeek: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      event: [],
    };
  },

  methods: {
    currentDay(day) {
      return moment().isSame(day, 'day');
    },
  },

  mounted() {
    axios.get('http://localhost:5000/events').then((res) => {
      this.event = res.data;
      // console.log(this.event);
    });
  },
};
</script>

<style lang="scss" scoped>
.calendar {
  display: grid;
  justify-content: center;
  grid-template: repeat(5, 90px) / repeat(7, 180px);
  color: #fff;
  &__day {
    min-width: 140px;
    min-height: 80px;
    border: 1px solid #404040;
    background-color: #1e1f21;
    color: #dcdcdc;
    padding: 8px;

    &:hover {
      background-color: #323337;
      cursor: pointer;
    }
  }
}
.week {
  background-color: #272829;
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
.toDay {
  border-radius: 18px;
  background-color: red;
}
</style>
