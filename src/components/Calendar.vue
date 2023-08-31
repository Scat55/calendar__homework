<template>
  <div id="calendar" class="calendar">
    <div class="calendar__day" v-for="(days, idx) in calendar">
      <div class="test">
        <div class="test2">{{ days.format('D') }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    calendar: {
      type: Array,
      default: [],
    },
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.calendar {
  display: grid;
  justify-content: center;
  grid-template: repeat(5, 90px) / repeat(7, 180px);

  &__day {
    min-width: 140px;
    min-height: 80px;
    border: 1px solid #404040;
    background-color: #1e1f21;
    color: #dcdcdc;
    padding: 8px;

    &:last-child {
      color: red;
    }

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
