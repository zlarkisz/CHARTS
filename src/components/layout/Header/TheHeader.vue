<template>
  <header class="header full-width">
    <div class="header__left">
      <div class="header__logo">
        <a href="/" class="header__logo_image">
          <Logo />
        </a>
        <div class="header__inform">
          <div v-for="(el, i) in inform" :key="`key-${i}`" class="header__inform_item">
            <a :href="el.url">{{ el.label }}</a>
          </div>
        </div>
      </div>
    </div>
    <div class="header__right">
      <div class="header__about">
        <a v-for="point in about" :key="point.label" :href="point.url" class="header__about_point">{{ point.label }}</a>
        <LanguageSelect :languages="languages" />
      </div>
      <div class="header__list">
        <div class="header__list_search" @click="search = !search">
          <Search />
        </div>
        <CollapseTransition :duration="500">
          <ul v-if="search">
            <li v-for="item in menuList" :key="item.label">
              <a :href="item.url">{{ item.label }}</a>
            </li>
          </ul>
        </CollapseTransition>
      </div>
    </div>
  </header>
</template>

<script>
import Logo from "@/assets/svg/logo.svg"
import Search from "@/assets/svg/search.svg"

import LanguageSelect from './LanguageSelect'

import { CollapseTransition } from 'vue2-transitions'

export default {
  name: 'TheHeader',

  components: {
    Logo,
    Search,
    LanguageSelect,
    CollapseTransition
  },

  data: () => ({
    inform: [
      { label: 'Inform.', url: '/inform'},
      { label: 'Connect.', url: '/connect'},
      { label: 'Inspire.', url: '/inspire'}
    ],
    about: [
      { label: 'Über uns', url: '/uns' },
      { label: 'Redaktion', url: '/redaktion' }
    ],
    languages: [
      { lang: 'DE' },
      { lang: 'EN' }
    ],
    menuList: [
      { label: 'DEsign+lifestyle', url: '/lifestyle' },
      { label: 'trends', url: '/trends' },
      { label: 'infodelight', url: '/infodelight' },
      { label: 'Smart Living', url: '/smart' }
    ],
    search: true
  })
}
</script>

<style lang="scss">
.header {
  padding: 20px 36px 15px;
  background-color: $c-white;
  @include flex(flex-start, space-between);
  color: $c-mine-shaft;

  @media only screen and(max-width: 1199px) {
    flex-direction: column;
  }

  &__right {
    height: 100%;
    @include flex(flex-end, space-between, column);

    @media only screen and(max-width: 1199px) {
      margin-top: 10px;
      align-items: flex-start;
    }
  }

  &__logo {
    margin-top: 32px;
    @include flex(flex-start, flex-start, column);

    @media only screen and(max-width: 768px) {
      margin-top: 0px;
    }
  }

  &__inform {
    margin-top: 13px;
    @include flex(center, flex-start);

    &_item {
      color: $c-mine-shaft;
      font: 400 13px/1.2 $f-main;

      &:not(:last-child) {
        margin-right: 13px;
      }
    }
  }

  &__about {
    @include flex(center, flex-end);
    font: 400 14px/1.2 $f-main;

    &_point {
      &:first-child {
        margin-right: 26px;
      }
      &:nth-child(n + 2) {
        margin-right: 20px;
      }
    }
  }

  &__list {
    margin-top: 32px;
    @include flex(center, flex-end);

    @media only screen and(max-width: 1199px) {
      margin-top: 10px;
    }

    @media only screen and(max-width: 768px) {
      align-items: flex-start;
      flex-direction: column;
    }

    &_search {
      margin-right: 25px;

      &:hover {
        cursor: pointer;
      }
    }

    ul {
      @include flex(center, flex-end, null, wrap);

      @media only screen and(max-width: 768px) {
        align-items: flex-start;
        flex-direction: column;
      }

      li {
        white-space: nowrap;
        text-transform: uppercase;
        position: relative;
        padding: 0 25px;
        
        &:last-child {
          padding-right: 0;
        }

        &::before {
          position: absolute;
          left: 0;
          top: 0;
          content: '';
          width: 1px;
          height: 100%;
          background-color: $c-mine-shaft;
        }

        @media only screen and(max-width: 768px) {
          margin-top: 10px;
        }
      }
    }
  }
}
</style>