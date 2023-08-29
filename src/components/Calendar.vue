<template>
  <div id="calendar" class="calendar"></div>
</template>

<script>
export default {
  data() {
    return {};
  },

  mounted() {},
};
</script>

<style lang="scss" scoped>
.calendar {
  display: grid;
  grid-template: repeat(7 1fr) / repeat(2 1fr);
  justify-content: center;
  gap: 20px;
  &__days:last-child,
  &__days:nth-child(6) {
    color: red;
  }
}
</style>
