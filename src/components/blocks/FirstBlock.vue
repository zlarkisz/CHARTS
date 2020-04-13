<template>
  <section class="first-block height full-width">
    <div class="first-block__left wrapper height">
      <BaseTopList :list="list" />

      <BaseTitle :level="2">
        Was hilft mir, Energie zu sparen und Spaß zu haben, bei mir zu Hause?
      </BaseTitle>

      <BaseDescription p="p">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut  dolor in reprehenderit in quia...
      </BaseDescription>
    </div>
    <div class="first-block__right wrapper height">
      <BaseTitle :level="2">
        A place called Inspiration.
      </BaseTitle>

      <BaseDescription p="p">
        Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit,
        sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam voluptatem.
      </BaseDescription>

      <BaseButton label="Über die Autoren" />

      <BaseButton label="Über das magazin" />
    </div>
  </section>
</template>

<script>
import BaseTitle from '@/components/base/BaseTitle'
import BaseDescription from '@/components/base/BaseDescription'
import BaseTopList from '@/components/base/BaseTopList'
import BaseButton from '@/components/base/BaseButton'

export default {
  name: 'FirstBlock',

  components: {
    BaseTitle,
    BaseDescription,
    BaseTopList,
    BaseButton
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
.first-block {
  color: $c-white;

  @include flex(flex-start, space-between);

  @media only screen and(max-width: 768px) {
    flex-direction: column;
  }

  &__left {
    background: center/cover no-repeat url('../../assets/img/first.jpeg');
    width: 75vw;

    @media only screen and(max-width: 1199px) {
      width: 50vw;
    }

    @media only screen and(max-width: 768px) {
      width: 100vw;
    }

    .title {
      font-size: 20px;
      text-align: center;
      max-width: 435px;
      line-height: 23px;
    }

    .description {
      max-width: 435px;
    }
  }

  &__right {
    width: 25vw;
    background-color: $c-mine-shaft;

    @include flex(flex-start !important);

    @media only screen and(max-width: 1199px) {
      width: 50vw;
    }

    @media only screen and(max-width: 768px) {
      width: 100vw;
    }

    .title {
      text-align: left;
    }

    .description {
      text-align: left;
      font-weight: 800;
      line-height: 24px;
      margin: 20px 0 13px;
    }
  }
}
</style>