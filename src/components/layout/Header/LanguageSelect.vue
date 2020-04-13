<template>
  <div class="language-select">
    <span
      v-for="(l, i) in languages"
      :key="l.lang"
      @click="changeLang(i)"
      :class="['language-select__lang', { 'language-select__lang_active': activeLanguage === i }]"
    >
      {{ l.lang }}
    </span>
  </div>
</template>

<script>
export default {
  name: 'LanguageSelect',

  props: {
    languages: {
      type: Array,
      default: () => ([])
    }
  },

  data: () => ({
    activeLanguage: 1
  }),

  methods: {
    changeLang (i) {
      this.activeLanguage = i
    }
  }
}
</script>

<style lang="scss">
.language-select {
  display: flex;
  &__lang {
    display: block;
    border: 1px solid $c-silver;
    box-sizing: border-box;
    padding: 5px;
    color: $c-silver;

    &:hover {
      cursor: pointer;
    }

    &_active {
      border: 1px solid $c-mine-shaft;
      color: $c-mine-shaft;
    }
  }
}
</style>