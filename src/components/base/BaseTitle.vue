<template>
  <component
    :is="`h${level}`"
    :class="['title', {'title_uppercase': uppercase}]"
  >
    <slot />
  </component>
</template>

<script>
export default {
  name: 'BaseTitle',

  props: {
    level: {
      type: [Number, String],
      default: 2
    },
    uppercase: {
      type: Boolean,
      default: false
    },
  }
}
</script>

<style lang="scss">
.title {
  font-weight: 800;
  text-align: center;
}
</style>