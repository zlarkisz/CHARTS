<template>
  <div id="app">
    <div class="container">
      <TheHeader />

      <FirstBlock />

      <SecondBlock />

      <div class="charts">
        <BaseChart type="pie" />

        <BaseChart type="bar" />

        <BaseChart type="line" />
      </div>
    </div>
  </div>
</template>

<script>
import TheHeader from './components/layout/Header/TheHeader'
import FirstBlock from './components/blocks/FirstBlock'
import SecondBlock from './components/blocks/SecondBlock'
import BaseChart from './components/base/BaseChart'

export default {
  name: 'App',

  components: {
    TheHeader,
    FirstBlock,
    SecondBlock,
    BaseChart
  }
}
</script>

<style lang="scss">
#app {
  .container  {
    color: $c-white;
  }
  .charts {
    @include flex(center, flex-start, none, wrap);
  }
}
</style>