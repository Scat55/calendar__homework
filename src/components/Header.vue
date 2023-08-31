<template>
  <div class="header">
    <div class="header__title">
      <span class="header__title-text"
        ><b>{{ title.format('MMMM') }} </b></span
      >
      <span class="header__title-subtext">{{ title.format('YYYY') }}</span>
    </div>
    <div class="header__btns">
      <button class="header__btn">&lt;</button>
      <button class="header__btn">Today</button>
      <button class="header__btn">&gt;</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: Object,
      default: {},
    },
  },

  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #1e1f21;
  color: #dcdddd;
  padding: 10px;

  &__title {
    padding: 1rem;
    &-text {
      font-size: 2rem;
      margin-right: 0.5rem;
    }
    &-subtext {
      font-size: 2rem;
    }
  }

  &__btn {
    border: unset;
    background-color: #565758;
    height: 28px;
    margin-right: 2px;
    border-radius: 4px;
    color: #e6e6e6;
    cursor: pointer;

    &:nth-child(2) {
      padding-right: 1rem;
      padding-left: 14px;
      font-weight: bold;
    }

    &:hover {
      background-color: #767779;
    }
  }
}
</style>
