<template>
  <component
    :is="p"
    :class="['description', {'description__top': top}]"
  >
    <slot />
  </component>
</template>

<script>
export default {
  name: 'BaseDescription',

  props: {
    p: {
      type: String,
      default: ''
    },
    top: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss">
.description {
  text-align: center;
  font: 500 14px/1.2 $f-main;
  margin-top: 40px;
}
</style>