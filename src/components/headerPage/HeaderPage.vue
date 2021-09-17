<template>
  <header class="header-page">
    <div class="header-page__inner">
      <a href="tel:+79046867942" class="header-page__phone-link">
        <svg
          class="header-page__phone-image"
          width="60"
          height="60"
          viewBox="0 0 60 60"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M29.8247 0C13.3541 0 0 13.4326 0 30C0 46.5671 13.3541 60 29.8247 60C46.2952 60 59.6491 46.567 59.6491 30C59.6492 13.4326 46.2952 0 29.8247 0ZM45.5741 43.7733L43.1861 46.1759C42.7597 46.6041 41.5113 46.8713 41.4713 46.8713C33.9167 46.9376 26.6428 43.9527 21.2983 38.5764C15.9392 33.1827 12.9684 25.8399 13.0482 18.2153C13.0482 18.2119 13.3216 16.9921 13.7475 16.5677L16.1354 14.1654C17.0092 13.2824 18.6878 12.8834 19.8637 13.2791L20.366 13.4476C21.5384 13.8429 22.7693 15.1469 23.0933 16.3482L24.2945 20.7828C24.6184 21.9876 24.1815 23.7016 23.3079 24.5806L21.7135 26.1847C23.2789 32.0141 27.8261 36.589 33.6225 38.1674L35.2164 36.563C36.0942 35.68 37.7976 35.2408 38.9928 35.5662L43.4008 36.7788C44.5954 37.1089 45.8915 38.3393 46.2844 39.5183L46.452 40.0308C46.8414 41.2103 46.4478 42.8983 45.5741 43.7733Z"
          />
        </svg>
      </a>
      <socials class="header-page__socials" in-header />
      <div class="header-page__menu-button">
        <menu-button class="header-page__menu-button" :items="itemsMenu" />
      </div>
      <nav class="header-page__navigation">
        <ul class="header-page__list">
          <li v-for="item in itemsMenu" class="header-page__item" :key="item.text">
            <a :href="item.link" class="header-page__link">{{ item.text }}</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Socials from '@/components/socials/Socials.vue';
import MenuButton from '@/components/menuButton/MenuButton.vue';
import { TLink } from '@/types';
import { menuLinksEnum } from '@/enums';

@Options({
  name: 'HeaderPage',
  components: { Socials, MenuButton },
})
export default class HeaderPage extends Vue {
  get itemsMenu(): TLink[] {
    return [
      {
        text: 'О себе',
        link: '#' + menuLinksEnum.about,
      },
      {
        text: 'Навыки',
        link: '#' + menuLinksEnum.skills,
      },
      {
        text: 'Образование',
        link: '#' + menuLinksEnum.education,
      },
      {
        text: 'Опыт работы',
        link: '#' + menuLinksEnum.experience,
      },
      {
        text: 'Достижения',
        link: '#' + menuLinksEnum.achievements,
      },
    ];
  }
}
</script>

<style lang="scss" scoped>
.header-page {
  width: 100%;
  position: fixed;
  z-index: 1;
  background: linear-gradient(
    180deg,
    rgba(249, 138, 35, 1) 0%,
    rgba(249, 138, 35, 0.7) 50%,
    rgba(249, 138, 35, 0.5) 75%,
    rgba(249, 138, 35, 0) 100%
  );

  &__inner {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: var(--container-width);
    padding: 28px 15px;
    margin: 0 auto;
  }

  &__list {
    display: flex;
  }

  &__item:not(:last-child) {
    margin-right: 33px;
  }

  &__link {
    font-size: 20px;
    line-height: 24px;
    &:hover {
      color: #fff;
    }
  }

  &__phone-image {
    fill: black;

    &:hover {
      fill: #fff;
    }
  }

  &__socials {
    display: none;
  }

  &__navigation {
    display: none;
  }
}

@media screen and (min-width: 1110px) {
  .header-page {
    &__socials {
      display: block;
    }

    &__phone-link {
      display: none;
    }

    &__menu-button {
      display: none;
    }

    &__navigation {
      display: block;
    }
  }
}
</style>
