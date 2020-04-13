<template>
  <section class="second-block height full-width">
    <div class="second-block__left wrapper height">
      <BaseTopList :list="list" />

      <BaseTitle :level="2">
        Was hilft mir, Energie zu sparen und Spaß zu haben, bei mir zu Hause?
      </BaseTitle>

      <BaseDescription p="p">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut  dolor in reprehenderit in quia...
      </BaseDescription>
    </div>
    <div class="second-block__right wrapper height">
      <BaseTopList :list="list" />

      <BaseTitle :level="2">
        Was hilft mir, Energie zu sparen und Spaß zu haben, bei mir zu Hause?
      </BaseTitle>

      <BaseDescription p="p">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut  dolor in reprehenderit in quia...
      </BaseDescription></div>
  </section>
</template>

<script>
import BaseTitle from '@/components/base/BaseTitle'
import BaseDescription from '@/components/base/BaseDescription'
import BaseTopList from '@/components/base/BaseTopList'

export default {
  name: 'SecondBlock',

  components: {
    BaseTitle,
    BaseDescription,
    BaseTopList
  },

  data: () => ({
    list: [
      { text: 'DEsign+lifestyle' },
      { text: 'Smart Living' }
    ]
  })
}
</script>

<style lang="scss">
.second-block {
  @include flex(flex-start, space-between);

  @media only screen and(max-width: 768px) {
    flex-direction: column;
  }

  &__left,
  &__right {
    min-width: 50%;
    max-width: 50%;
    
    @media only screen and(max-width: 768px) {
      min-width: 100%;
    }

    .title,
    .description {
      max-width: 445px;
    }
  }

  &__left {
    background: center/cover no-repeat url('../../assets/img/second.jpeg');
  }

  &__right {
    background: center/cover no-repeat url('../../assets/img/third.jpeg');
  }
}
</style>