<template>
  <ul class="top-list">
    <li v-for="item in list" :key="item.text" class="top-list__item">
      {{ item.text }}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'BaseTopList',

  props: {
    list: {
      type: Array,
      default: () => ([])
    }
  }
}
</script>

<style lang="scss">
.top-list {
  margin-top: 75px;
  margin-bottom: 40px;
  @include flex(center, center);

  &__item {
    font: 800 14px/1.2 $f-main;
    position: relative;
    padding: 0 10px;
    text-transform: uppercase;

    &::before {
      top: 0;
      left: 0;
      content: '';
      position: absolute;
      width: 1px;
      height: 100%;
      background-color: $c-white;
    }

    &::after {
      top: 0;
      right: -1px;
      content: '';
      position: absolute;
      width: 1px;
      height: 100%;
      background-color: $c-white;
    }
  }
}
</style>