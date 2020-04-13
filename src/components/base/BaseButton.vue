<template>
  <div class="button">
    <a :href="link" class="button__link">{{ label }}</a>
  </div>
</template>

<script>
export default {
  name: 'BaseButton',

  props: {
    link: {
      type: String,
      default: '/'
    },
    label: {
      type: String,
      default: ''
    },
  }
}
</script>

<style lang="scss">
.button {
  &__link {
    display: block;
    padding: 11px 34px 11px 17px;
    border: 1px solid $c-white;
    min-width: 152px;
    box-sizing: border-box;
    margin-top: 9px;
  }
}
</style>