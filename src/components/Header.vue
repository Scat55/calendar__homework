<template>
  <div>
    <ul class="buttons">
      <li class="buttons__list" v-for="button in buttons">{{ button }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      buttons: ['Day', 'Week', 'Month', 'Year'],
    };
  },
};
</script>

<style lang="scss" scoped>
.buttons {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;

  &__list {
    list-style: none;
    border: 1px solid#cecece;
    border-radius: 4px;
    padding: 8px;
    cursor: pointer;
    background-color: #443a3a;
    color: #fff;
  }
}
</style>
